# How to secure a web app with HTTP headers

TIL in progress.

Based on info found [here](https://www.smashingmagazine.com/2017/04/secure-web-app-http-headers/)

Web apps are constantly subject to cyber attacks. Malicious code can be implemented by hackers to steal information but here are a few ways to improve security using HTTP headers.

#### Disabling caching of confidential resources:

Caching allows you to optimize the performance of your web app by storing data in a cache (temporary storage area) instead of having to request that data every time you load the same page.
However if you cache sensitive information, it can lead to vulnerabilities.

When dealing with that kind of information, 3 headers should be used:

* Cache-control: `cache-control: no-cache, no-store, must-revalidate`. Using these 3 directives will make sure that the info is not cached, not stored and if the response is somehow cached, the cache must be revalidated on the origin server.

* Pragma: `no-cache`. If HTTP 1.1 is not supported, this allows backward compatibility.

* Expires: `-1`. This headers usually specifies a timestamp, however, by using -1, we make sure the client considers the response as stale and avoids caching.

```javascript
function requestHandler(req, res) {
	res.setHeader('Cache-Control','no-cache,no-store,max-age=0,must-revalidate');
	res.setHeader('Pragma','no-cache');
	res.setHeader('Expires','-1');
}
```

#### Enforcing HTTPS

An unsecure connection can lead to cookie theft.
To avoid these attacks and ensure connection over HTTPS, we can use the HSTS (HTTP Strict Transport Security) header. It makes sure all communications with the origin host use HTTPS.

HSTS directives include:

*


#### Enabling XSS Filtering

#### Controlling framing

#### Prevent content-type sniffing
