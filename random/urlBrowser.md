# What happens when you enter a URL in the browser and press ENTER.

Let's say we want to access Google maps.

## 1) We start by entering maps.google.com in the address bar of the browser and press ENTER.

## 2) The browser starts by checking the cache for a DNS record to find the corresponding IP address for maps.google.com

**DNS** (Domain Name System) is a database that works a little bit like a phone book with website URLs as the name and IP addresses as the phone number.

Each website has a unique IP address. This IP address belongs to the computer which hosts the server of the website we are requesting access to.

**The main purpose of DNS is to make IP addresses more readable by humans.**
You can access websites by knowing their IP address but it is harder to remember 209.85.227.104 than maps.google.com.
The DNS does the mapping between the URL you enter and its corresponding IP address.

To find an IP address, the browser checks 4 caches:

1) The **browser cache**.The browser maintains a repository of DNS records for a fixed duration of time for websites you have previously visited.

2) The **OS cache**. If a record is not found in the browser cache, the browser makes a system call to the computer OS to fetch the record as the OS also maintains a cache for DNS records.

3) The **router cache**. The router also maintains a DNS cache so if it is not found in the browser or the computer, the browser will check in the router cache.

4) The **ISP cache**. Your ISP maintains its own DNS server which includes a cache of DNS records.


## 3) If the URL requested is not in the cache, ISP's DNS server will execute a DNS query to find the IP address of the server that hosts maps.google.com.

DNS queries search multiple DNS servers on the internet until it finds the correct IP address.

This type of search is called **recursive search** since the search will continue repeatedly from DNS server to DNS server until it either finds the IP address or returns an error indicating it was unable to find it.

In this situation, the IPS's DNS server is called a **DNS recursor** whose responsibility is to find the proper IP address by asking other DNS servers for an answer.
The other DNS servers are called **name server** as they perform a DNS search based on the domain architecture of the website domain name.

---

### Domain architecture

---

![domain architecture](https://cdn-images-1.medium.com/max/1600/0*udK6jZ3PjlhjqW8U.png)

Many websites contain a third-level domain, a second-level domain and a top-level domain. Each level contains their own name server which is queried during the **DNS lookup search**.

For our example with maps.google.com, the DNS recursor will contact the root name server. The root name server will redirect to **.com** domain name server.

**.com** name server will redirect to **google.com** name server.

**google.com** name server will find the matching IP address for maps.google.com in its DNS records and return to your DNS recursor which will send it back to your browser.

These multiple requests are sent using **small data packets** which contain information like the content of the request and the IP address it is destined for.

The packets travel through multiple networking equipment that uses routing tables to figure out the fastest way for these packets to reach the destination. If these packets get lost, you'll get a request failed error, otherwise, they will reach the correct DNS server, grab the correct IP address and come back to the browser.

## 4) Browser initiates a TCP connection with the server.

Once the browser got the correct IP address, it will build a connection with the server that matches IP address to transfer information. Internet protocols are used to build these connections and **TCP** is the **most common protocol used for HTTP requests**.

To transfer data packets between your computer (client) and the server, it is important to have a TCP connection established using a process called the **TCP/IP three-way handshake**.
This 3 steps process allows the client and server exchange to **SYN(synchronize)** and **ACK(acknowledge)** messages to establish a connection.

1. Client machine sends a SYN packet to the server over the internet asking if it is open for new connections.

2. If the server has open ports that can accept and initiate new connections, it will respond with an ACKnowledgment of the SYN packet using a SYN/ACK packet.

3. The client will receive this packet from the server and will acknowledge it by send an ACK packet.

Once this is done, a TCP connection is establised to transfer data.

## 5) The browser sends a HTTP request to the web server.

To start transferring data, the browser will send a GET request asking for maps.google.com web page.
The request will also contains additional information such as browser identification (*user-agent*), type of requests and connections headers asking it to keep the TCP connection alive for additional requests.

## 6) The server handles the request and sends back the response.

The server contains a web server which receives the request from the browser and passes it to a request handler and generate a response.
The request handler is a program that reads the request, its headers and cookies to check what is being requested and updates the information on the server as needed. It then assembles a response in a particular format (JSON, XML, HTML).

## 7) The server sends out a HTTP response.

The server response contains the web page you requested as well as the status code, compression tyep, how to cache the page, cookies, privacy info, etc...

The 1st line is usually the status code. there are 5 types of status codes:

* 1xx: informational message only.
* 2xx: success.
* 3xx: redirection to another URL.
* 4xx: error on the client's part.
* 5xx: error on the server's part.


## 8) The browser displays the HTML content.

The browser displays HTML content in phases.

First, it will render the bare HTML.
Then, it will look for tags and send out GET requests for additional elements such as images, CSS, etc...
These static files are cached in the browser so it doesnt have to fetch them again next time.

---


Note highly inspired by [this Medium article](https://medium.com/@maneesha.wijesinghe1/what-happens-when-you-type-an-url-in-the-browser-and-press-enter-bb0aa2449c1a).
