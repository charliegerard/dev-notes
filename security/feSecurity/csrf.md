# Cross-Site Request Forgery (CSRF)

CSRF (also pronounced sea-surf) vulnerabilities can be used to trick a user's browser into performing an unwanted action on your site.

CSRF attacks can spread themselves as a worm.

Example scenario:

Posting on Twitter uses GET requests with the content of the message in the URL to post it on your timeline.
An attacker realises that and creates a link with a malicious message in the url. They send you an email with something you click on without realising they embedded the URL in the email.
Clicking on the content of the email actually posted a new post on your Twitter timeline without you realising and now everybody clicking on the link inside your tweet, ends up posting the same tweet, creating a worm.

A CSRF attack occurs when a malicious actor tricks a user into clicking on a link, or running some code that triggers a **forged HTTP request**. **The malicious code is typically hosted on a website owned by the attacker on another domain, hence "cross-site".**


## Usage:

CSRF attacks can:

* Steal confidential data.
* Spread worms on social media.
* Install malware on mobile phones.

CSRF attacks are hard to spot as they are disguised as normal user actions.


## Protection

Protecting against CSRF attacks involves **making sure GET requests are side-effects free** and ensuring that non-GET requests can only be originated from your client-side code.

### REST

REST (Representation State Transfer) is a series of design principles that assign certain types of action (view, create, delete, update) to different HTTP verbs.
REST insists that GET request are used only to view resources, keeping them side-effect free.

### Anti-forgery tokens

POST requests can still be sent to your site from scripts and pages hosted on other domains. To ensure you're handling valid HTTP requests, you need to include a **secret** and **unique** token with each HTTP response and have the server verify the token when passed back in next requests that use the POST method.

**Anti-forgery tokens are typically random numbers stored in a cookie or on the server as they are written ou to a hidden HTML field. If the values attached to the inbound request and the one stored in the cookie are identical, the server will accept the HTTP request.**

### Ensure Cookies are sent with the SameSite attribute

```
Set-Cookie: CookieName=CookieValue; SameSite = Lax;
Set-Cookie: CookieName=CookieValue; SameSite = Strict;
```

`Strict` is the most secure. It means any request initiated by 3rd party domains to your domain will have cookies stripped by the browser.

`Lax` allows requests from third-party domains to your domain to have cookies attached, but ONLY for GET requests.
