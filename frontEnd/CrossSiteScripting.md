# Cross-Site Scripting (XSS)

Cross-Site Scripting is a form of injection attack where the attacker exploits vulnerabilities on a webpage to execute scripts to steal information like credentials, session information, keystrokes, etc...

3 types of XSS attacks:

#### Reflected attacks.

The malicious code (script) is sent as an input to the server that then reflects the code back to the user and displays the information somewhere on the page.
The attacker's payload has to be part of the request sent to the server and reflected back in such a way that the HTTP response includes the payload from the HTTP request.

This can happen when a user clicks on a malicious link.

Example:

Phishing emails and social networks are usually used to deliver reflected attacks. Users are lured to make a request to the server which contains the XSS payload and ends-up executing the script that is then reflected in the browser.

#### DOM-based attack

The script is injected into the DOM on a website. Either as input in input boxes or as parameters in urls.
This type of attack does not modify the server's response but modifies the client-side code.

Example:

If we have a site with a form that allows the user to pick a preferred language.
A default language parameter is provided in the query string like this:

```
http://www.some.site/page.html?default=French
```

However, a DOM based XSS can be done by sending the following link to a victim:

```
http://www.some.site/page.html?default=<script>alert(document.cookie)</script>
```

When the user clicks on this link, the request is sent to the server with the parameters:

```
/page.html?default=<script>alert(document.cookie)</script>
```

When the server responds to the request, the original JS code does not expect the default parameter to contain HTML markup so it simply echoes it to the DOM at runtime and the browser executes the script.

```
alert(document.cookie)
```

The HTTP response sent back from the server does not contain the attack. The payload happens on the client-side at runtime.


#### Stored Attack:

Attacker injects malicious code through data input stored in the database.

Example:

On a popular forum, the attacker injects malicious code in the input fields to create a comment.

```
<input type="text" onmouseover="window.location.href=("http://google.com")"
```

Once the comment is posted and stored in the database, if the user clicks on the comment to view it and hovers over the text, the user is redirected to the url injected.
