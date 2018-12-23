# ClickJacking

ClickJacking attacks **trick the user into performing an action they did not intend**, typically by **rendering an invisible page element on top of the action** the user thinks they are performing.

## Usage
---

ClickJacking can be used to:

* Steal login credentials by rendering a fake login box on top of the real one.
* Trick the users into turning on their webcam or microphone.
* Promote online scams by tricking people into clicking on things.
* Spread malware by diverting users to malicious download links.

## Protection
---

ClickJacking attacks wrap your website into an iframe, then renders invisible elements on top. To avoid that, we need to make sure the website cannot be wrapped in an iframe by a malicious site. We can do this using HTTP headers.

### X-frame options

This HTTP header can be used to indicate if your web page is allowed to be rendered inside a `<frame>`, `<iframe>` or `<object>`.

3 values can be used:

* `DENY`: the page cannot be displayed in a frame.
* `SAMEORIGIN`: the page can only be displayed in a frame on the same origin as the page.
* `ALLOW-FROM *uri*`: the page can only be displayed in a frame on specific origins.

### Content Security Policy

This HTTP header is used to whitelist individual domains from which resources can be loaded, and domain that are permitted to embed a page.

The `frame-ancestors` directive can control where your site can be embedded:

* `Content-Security-Policy: frame-ancestors 'none'`: page cannot be displayed in a frame.
* `Content-Security-Policy: frame-ancestors 'self'`: page can be displayed in a frame only on same origin.
* `Content-Security-Policy: frame-ancestors *uri*'`: page can be displayed only on specific origins.

### Frame-killing

On older browsers, a frame-killing JS script was added on pages to prevent them being used in foreign iframes.

```html
<style>
  /* Hide page by default */
  html { display : none; }
</style>

<script>
  if (self == top) {
    // Everything checks out, show the page.
    document.documentElement.style.display = 'block';
  } else {
    // Break out of the frame.
    top.location = self.location;
  }
</script>
```
