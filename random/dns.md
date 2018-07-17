# How does DNS work?

DNS or **Domain Name System / Domain Name Servers** work a little bit like an address book.

As you enter `google.com` in your address bar, the browser needs to do some work to be able to access `google.com`'s web server. It needs to find its IP address. The DNS will do a lookup to find the corresponding IP address.

However, as millions of requests are executed at the same time, there is not only 1 DNS server responsible for this lookup.

DNS is more of a **distributed system** with some levels of hierarchy.

* Step 1: **Root servers**: divided in 13 groups. If you ask who is `google.com`, they won't know but they will know which servers are responsible for `.com` domains. It finds the IP address for the top-level domain server.

* Step 2: **TLD (Top-level domain)** layer. Bunch of server are responsible for `.net` domains, others for `.com` domains, etc... These won't have a straight answer about who `google.com` is but they will have a bunch of IP addresses for servers responsible for `google.com` and its subdomains.

* Step 3: **Domain name layer**. This server will have the IP address of `google.com` and the browser will now be able to contact `google.com`'s web server using this IP address.
