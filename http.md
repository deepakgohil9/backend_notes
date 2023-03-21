## 💫 HTTP Protocol

HTTP is an application layer protocol for transmitting hyper-media documents. It was designed for communication between a web browser and the web server. HTTP follows the client-server architecture where the client sends the request and waits until it receives the response. HTTP is a stateless protocol, meaning that the server does not keep any data (state) between two requests. 

HTTP protocol consists of the following:

*   HTTP header
*   HTTP request method
*   HTTP status code

## 💫 Evolution of HTTP protocol

### ✅ HTTP/0.9 – The one-line protocol

The initial version of HTTP had no version number; it was later called 0.9 to differentiate it from later versions. HTTP/0.9 was extremely simple: requests consisted of a single line and started with the only possible method `GET` followed by the path to the resource. The full URL wasn't included as the protocol, server, and port weren't necessary once connected to the server. 

```html
GET /mypage.html

<html>
  A very simple HTML page
</html>
```

Unlike subsequent evolutions, there were no HTTP headers. This meant that only HTML files could be transmitted. There were no status or error codes. If there was a problem, a specific HTML file was generated and included a description of the problem for human consumption.

### ✅ HTTP/1.0 – Building extensibility

*   The concept of HTTP headers was introduced for both requests and responses. Metadata could be transmitted and the protocol became extremely flexible and extensible.
*   A status code line was also sent at the beginning of a response. This allowed the browser itself to recognize the success or failure of a request and adapt its behavior accordingly. For example, updating or using its local cache in a specific way.
*   Documents other than plain HTML files can be transmitted thanks to the `Content-Type` header.

At this point in time, a typical request and response looked like this:

```html
GET /mypage.html HTTP/1.0
User-Agent: NCSA_Mosaic/2.0 (Windows 3.1)

200 OK
Date: Tue, 15 Nov 1994 08:12:31 GMT
Server: CERN/3.0 libwww/2.17
Content-Type: text/html
<HTML>
A page with an image
 <IMG SRC="/myimage.gif">
</HTML>
```

It was followed by a second connection and a request to fetch the image (with the corresponding response):

```html
GET /myimage.gif HTTP/1.0
User-Agent: NCSA_Mosaic/2.0 (Windows 3.1)

200 OK
Date: Tue, 15 Nov 1994 08:12:32 GMT
Server: CERN/3.0 libwww/2.17
Content-Type: text/gif
(image content)
```

### ✅ HTTP/1.1 – The standardized protocol

HTTP/1.1 clarified ambiguities and introduced numerous improvements:

*   A connection could be reused, which saved time. It no longer needed to be opened multiple times to display the resources embedded in the single original document.
*   Pipelining was added. This allowed a second request to be sent before the answer to the first one was fully transmitted. This lowered the latency of communication.
*   Chunked responses were also supported.
*   Additional cache control mechanisms were introduced.
*   Content negotiation, including language, encoding, and type, was introduced. A client and a server could now agree on which content to exchange.
*   Thanks to the `Host` header, the ability to host different domains from the same IP address allowed server collocation.

One of the majority changes is that HTTP/1.1 introduces a `Keep-Alive` the header which allows reusing the connection for the next request. Unlike HTTP/1.0 where each request creates a connection and then closes the connection once it receives a response from the server. Now we can create a connection and then send multiple requests one after another on the same connection. After that, at last, we close the connection once we feel that we will no longer need it.

A typical flow of requests, all through one single connection, looked like this:

```html
GET /en-US/docs/Glossary/Simple_header HTTP/1.1
Host: developer.mozilla.org
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.9; rv:50.0) Gecko/20100101 Firefox/50.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: en-US,en;q=0.5
Accept-Encoding: gzip, deflate, br
Referer: https://developer.mozilla.org/en-US/docs/Glossary/Simple_header

200 OK
Connection: Keep-Alive
Content-Encoding: gzip
Content-Type: text/html; charset=utf-8
Date: Wed, 20 Jul 2016 10:55:30 GMT
Etag: "547fa7e369ef56031dd3bff2ace9fc0832eb251a"
Keep-Alive: timeout=5, max=1000
Last-Modified: Tue, 19 Jul 2016 00:59:33 GMT
Server: Apache
Transfer-Encoding: chunked
Vary: Cookie, Accept-Encoding

(content)

GET /static/img/header-background.png HTTP/1.1
Host: developer.mozilla.org
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.9; rv:50.0) Gecko/20100101 Firefox/50.0
Accept: */*
Accept-Language: en-US,en;q=0.5
Accept-Encoding: gzip, deflate, br
Referer: https://developer.mozilla.org/en-US/docs/Glossary/Simple_header

200 OK
Age: 9578461
Cache-Control: public, max-age=315360000
Connection: keep-alive
Content-Length: 3077
Content-Type: image/png
Date: Thu, 31 Mar 2016 13:34:46 GMT
Last-Modified: Wed, 21 Oct 2015 18:27:50 GMT
Server: Apache

(image content of 3077 bytes)
```
