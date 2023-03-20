## 💫 HTTP Server

An HTTP server is software that understands URLs (web addresses) and HTTP (the protocol your browser uses to view webpages). An HTTP server can be accessed through the domain names of the websites it stores, and it delivers the content of these hosted websites to the end user's device.

  
## 💫 Web Server

1.  On the hardware side, a web server is a computer that stores web server software and a website's component files (for example, HTML documents, images, CSS stylesheets, and JavaScript files). A web server connects to the Internet and supports physical data interchange with other devices connected to the web.
2.  On the software side, a web server includes several parts that control how web users access hosted files. At a minimum, this is an _HTTP server_.
  
  
    ![Basic representation of a client/server connection through HTTP](https://developer.mozilla.org/en-US/docs/Learn/Common_questions/Web_mechanics/What_is_a_web_server/web-server.svg)

                                                                       
                                                                       
To publish a website, you need either a static or a dynamic web server.

A **static web server**, or stack, consists of a computer (hardware) with an HTTP server (software). We call it "static" because the server sends its hosted files as-is to your browser.

A **dynamic web server** consists of a static web server plus extra software, most commonly an _application server_ and a _database_. We call it "dynamic" because the application server updates the hosted files before sending content to your browser via the HTTP server.

For example, to produce the final webpages you see in the browser, the application server might fill an HTML template with content from a database. Sites like MDN or Wikipedia have thousands of webpages. Typically, these kinds of sites are composed of only a few HTML templates and a giant database, rather than thousands of static HTML documents. This setup makes it easier to maintain and deliver the content.

Apart from filling out the template nowadays, there is another way to serve the webpage. In this we have two different webservers one which contains all the frontends (HTML, CSS, assets and JS) and another has backend APIs. The frontend hits the backend API to fetch dynamic data and the populate it into the webpage.
