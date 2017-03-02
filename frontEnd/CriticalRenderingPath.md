# Critical Rendering Path (CRP)

**Number of steps the browser has to take to render a page.**

If we have a very simple HTML file not requesting any assets, this is what our CRP would look like:

<img src="https://res.cloudinary.com/practicaldev/image/fetch/s--Bw3-ns0r--/c_limit,f_auto,fl_progressive,q_auto,w_725/https://github.com/sanjsanj/otfe-assets/blob/master/otfe-crp-1.png%3Fraw%3Dtrue">

The browser makes a GET request to get our 1kb HTML file with no CSS or JS and is then able to build the DOM and render the page.

### Path length

The first of the 3 CRP metrics is **path length**.

If our file looks like the code sample below, our path length is 1 as the browser only needs to do 1 request to get our HTML file.
```html
<html>
  <head>Page</head>
  <body>
    <h1>Hello</h1>
  </body>
<html>
```

Now let's add a bit of internal styles and JS.

```html
<html>
  <head>Page</head>
  <style>
    h1{
      color: pink;
    }
  </style>
  <body>
    <h1>Hello</h1>
  </body>

  <script>
    window.onload = function(){
      console.log('hello')
    }
  </script>
<html>
```

Our CRP diagram would now look like this:

<img src="https://res.cloudinary.com/practicaldev/image/fetch/s--dZEc0xuy--/c_limit,f_auto,fl_progressive,q_auto,w_725/https://github.com/sanjsanj/otfe-assets/blob/master/otfe-crp-2.png%3Fraw%3Dtrue">

As we added some CSS and JS, the browser now needs to **build the CSSOM** and **execute the script** which adds 2 extra steps but does not affect the length of our CRP.

### Critical Bytes

The second metric is called **Critical Bytes**.
It measures how many bytes have to be transferred to render the page. Not all the bytes that are downloaded, just the ones needed to render the page.

Even if adding some internal CSS and JS does not affect the length of our CRP, this is not a good solution as it is not scalable and assets should be external.

So if we load styles and scripts from outside the HTML file, we would have this:


```html
<html>
  <head>Page</head>
  <link rel="stylesheet" href="styles.css"></link>
  <script src="index.js" async></script>
  <body>
    <h1>Hello</h1>
  </body>

  <script src="app.js"></script>
<html>
```

Our CRP diagram now looks like this:

<img src="https://res.cloudinary.com/practicaldev/image/fetch/s--O1Uocdtw--/c_limit,f_auto,fl_progressive,q_auto,w_725/https://github.com/sanjsanj/otfe-assets/blob/master/otfe-crp-3.png%3Fraw%3Dtrue">

The browser requests our HTML and starts building the DOM. When it finds any external resources, the preload scanner starts and the downloading of external assets starts with priority on CSS and JS assets.

If the `async` attribute is used on a script tag, the loading of that asset will not be a priority and will happen in another thread. It won't affect the CRP.

### Critical files

The third metric is **Critical Files**. It is the total number of files the browser has to download to render the page.
In our latest code sample, this number is 3: the HTML, external CSS and JS files. The `async` script does not count.

HTTP1 limits the number of file that can be downloaded at a time to 6 on Chrome.
Also, the TCP protocol limits the amount of data that can be transferred in one round trip to 14kb for all requests including HTML, CSS and scripts. If our HTML or accumulation of resources exceeds 14kb, we need to make additional round trips to fetch them.


### Example with big web app

```html
<!DOCTYPE html>
<html>
  <head>
    <title>The "Click the button" page</title>
    <link rel="stylesheet" href="styles.css">     // 14kb
    <link rel="stylesheet" href="main.css">       // 2kb
    <link rel="stylesheet" href="secondary.css">  // 2kb
    <link rel="stylesheet" href="framework.css">  // 2kb
    <script type="text/javascript" src="app.js"></script>  // 2kb
  </head>

  <body>
    <button type="button">Click me</button>

    <script type="text/javascript" src="modules.js"></script>    // 2kb
    <script type="text/javascript" src="analytics.js"></script>  // 2kb
    <script type="text/javascript" src="modernizr.js"></script>  // 2kb
  </body>
</html>
```

If we imagine the HTML is 2kb worth of data, it is way below the 14kb limit and can be loaded in a first round trip of the CRP and the browser can start building our DOM with the 1 critical file, our HTML.

<img src="https://res.cloudinary.com/practicaldev/image/fetch/s--nnSWBOgG--/c_limit,f_auto,fl_progressive,q_auto,w_725/https://github.com/sanjsanj/otfe-assets/blob/master/otfe-crp-4-1.png%3Fraw%3Dtrue">

`CRP Metrics: Length 1, Files 1, Bytes 2kb`

Then, the browser picks up the CSS file and thanks to the **preload scanner** identifies all other external resources and makes a request to begin downloading them.
BUT, the first CSS file is 14kb which reaches the limit of payload for a round trip, so that's 1 CRP by itself.

<img src="https://res.cloudinary.com/practicaldev/image/fetch/s--aaT5R6BA--/c_limit,f_auto,fl_progressive,q_auto,w_725/https://github.com/sanjsanj/otfe-assets/blob/master/otfe-crp-4-2.png%3Fraw%3Dtrue">

`CRP Metrics: Length 2, Files 2, Bytes 16kb`

It then goes on and downloads resources. The remainder weigh of the resources is under 14kb so it could make one round trip but the amount of assets left is 7 and as we're not using HTTP and we're on Chrome, the limit is 6 in this round trip.

<img src="https://res.cloudinary.com/practicaldev/image/fetch/s--TWwiWC3J--/c_limit,f_auto,fl_progressive,q_auto,w_725/https://github.com/sanjsanj/otfe-assets/blob/master/otfe-crp-4-3.png%3Fraw%3Dtrue">

`CRP Metrics: Length 3, Files 8, Bytes 28kb`

In a last round trip, the final file is downloaded and the DOM is rendered.

<img src="https://res.cloudinary.com/practicaldev/image/fetch/s--zJNI3UQ---/c_limit,f_auto,fl_progressive,q_auto,w_725/https://github.com/sanjsanj/otfe-assets/blob/master/otfe-crp-4-4.png%3Fraw%3Dtrue">

`CRP Metrics: Length 4, Files 9, Bytes 30kb`
