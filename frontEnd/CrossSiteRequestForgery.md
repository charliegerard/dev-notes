# Cross-Site Request Forgery (CSRF)

A Cross-Site Request Forgery is an attack that forces an end user to execute unwanted actions on a web application in which they're logged in.
This type of attacks targets state-changing requests, not theft of data.
For example, a CSRF attack can force the user to perform a state change request like transferring funds, changing email and password, etc...

This type of attack can be implemented inside a website using an IMG or IFRAME tag in a field that accepts HTML.

Examples:

In the scenario of a user wanting to transfer $100 to another user on bank.com, an attacker wants to trick the user to transfer that money to them instead.

#### GET request:

If the web application is designed to use GET requests to transfer parameters and execute actions, the money transfer operation might look like this:

```
GET http://www.bank.com/transfer?acct=ROB&amount=100 HTTP/1.1
```

If the attacker wants to exploit this vulnerability, they can manipulate the URL so it now is:

```
http://www.bank.com/transfer?acct=MARIE&amount=10000
```

Now the attacker has to trick the user to executing this request by sending an unsolicited email with a link like:

```html
<a href="http://www.bank.com/transfer?acct=MARIE&amount=10000">Click!</a>
```

OR by adding a fake 0x0 image.

```html
<img src="http://www.bank.com/transfer?acct=MARIE&amount=10000" width="0" height="0" border="0">
```

If the image is included in an email, the user would not see anything but the browser will still execute the script.

#### POST request:

If the website uses POST, the request would look like this:

```
POST http://bank.com/transfer.do HTTP/1.1

acct=ROB&amount=100
```

Such a request can be delivered using a form:

```html
<form action="http://bank.com/transfer.do" method="POST">
<input type="hidden" name="acct" value="MARIE"/>
<input type="hidden" name="amount" value="100000"/>
<input type="submit" value="View my pictures"/>
</form>
```
