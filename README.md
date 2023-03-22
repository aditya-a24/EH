# Q1. What is request and response?
      
- In the context of computer networking, a request and response are two fundamental concepts that govern the flow of data between client and server applications. A request is a message sent by a client application to a server, requesting some action or information. A response, on the other hand, is a message sent by a server application to a client, providing the requested information or indicating the success or failure of the requested action.

Let's take a closer look at each of these concepts:

- Request:
A request is a message that a client application sends to a server application, asking it to perform some action or provide some information. Requests typically  include a method (such as GET, POST, PUT, DELETE) that specifies the type of action to be performed, a URL that identifies the resource or endpoint to be accessed, and optionally, some data or parameters that the server needs to perform the requested action.
For example, when you enter a URL in your web browser, your browser sends an HTTP GET request to the web server, asking it to provide the HTML document for that URL.

Here's an example of a request:

Suppose you're using a web browser to access a website, and you want to view a specific page on that website. When you enter the URL for that page in your browser's address bar and press enter, your browser sends a request to the web server hosting the website, asking it to provide the content for that page.

Here's what that request might look like:
```
GET /example-page HTTP/1.1
Host: www.example.com
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:87.0) Gecko/20100101 Firefox/87.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,*/*;q=0.8
Accept-Language: en-US,en;q=0.5
Accept-Encoding: gzip, deflate, br
Connection: keep-alive
Upgrade-Insecure-Requests: 1
```

In this example, the request uses the GET method to ask for the content of the "/example-page" URL on the "www.example.com" host. The request also includes some additional information, such as the user agent string (indicating the browser and operating system being used), the accepted content types and encodings, and various headers related to the connection and security.

- Response:
A response is a message that a server application sends to a client application, providing the requested information or indicating the success or failure of the requested action. Responses typically include a status code (such as 200 OK, 404 Not Found, 500 Internal Server Error) that indicates the result of the requested action, some data or content that the server provides as a response to the request, and optionally, some metadata that provides additional information about the response.
For example, when you enter a URL in your web browser, the web server sends an HTTP response back to your browser, providing the HTML document for that URL, along with some metadata such as the content type and length of the response.

Here's an example of a response:

Continuing from the previous example of a request for the "/example-page" URL on the "www.example.com" host, let's say that the server successfully processes the request and sends back a response containing the HTML content for that page. Here's what that response might look like:

```php
HTTP/1.1 200 OK
Content-Type: text/html; charset=UTF-8
Content-Length: 1234
Date: Mon, 22 Mar 2023 12:00:00 GMT
Server: Apache/2.4.6 (CentOS)

<!DOCTYPE html>
<html>
<head>
	<title>Example Page</title>
</head>
<body>
	<h1>Hello, world!</h1>
	<p>This is an example page.</p>
</body>
</html>
```

In this example, the response uses the HTTP/1.1 protocol and has a status code of 200 OK, indicating that the request was successful and the requested content is included in the response. The response also includes some additional metadata, such as the content type (text/html) and length (1234 bytes) of the response, the date and time that the response was generated, and the server software and version used to generate the response.

The actual content of the response is the HTML code for the example page, including a title, header, and body section with some sample content. This content would be rendered by the browser to display the example page to the user.

In summary, a request is a message sent by a client application to a server, requesting some action or information, while a response is a message sent by a server application to a client, providing the requested information or indicating the success or failure of the requested action. These two concepts are fundamental to the functioning of client-server applications and are used extensively in web development, API development, and other areas of computer networking.


# Q2. What happens when your browser loads a website?

- When you load a website in your browser, several things happen behind the scenes. Here's a general overview of the steps involved:

    ## 1. DNS Lookup:
    Your browser begins by performing a DNS (Domain Name System) lookup to translate the domain name in the URL (such as "www.example.com") into an IP addressthat can     be used to locate the server hosting the website.

    ## 2. Establishing a Connection:
    Once the IP address is obtained, your browser establishes a TCP (Transmission Control Protocol) connection with the server on the specified port (usually port 80       for HTTP or port 443 for HTTPS).

    ## 3. Sending the Request:
    After the connection is established, your browser sends an HTTP request to the server, specifying the method (such as GET or POST), the requested URL, and any         additional headers or data that may be needed.

    ## 4. Processing the Request:
    The server receives the request and processes it, retrieving any necessary data or resources and generating a response.

    ## 5. Receiving the Response:
    The server sends the HTTP response back to your browser, typically including headers and metadata along with the requested content.

    ## 6. Rendering the Content:
    Your browser receives the response and begins rendering the content, parsing any HTML, CSS, and JavaScript code and displaying the page to the user.

    ## 7. Loading Additional Resources:
    If the page includes additional resources such as images, videos, or scripts, your browser may need to make additional requests to the server to retrieve those         resources.

    ## 8. Interactivity:
    Once the page is fully loaded, your browser may continue to interact with the server and update the page dynamically in response to user input or other events.

These steps happen very quickly and are largely invisible to the user, but they are essential to the functioning of the web and the delivery of content to millions of users around the world.


# Q3. How does a website know whose logged in? 

When you log in to a website, the website creates a unique identifier for you called a session ID. This session ID is like a special code that is specific to you and is stored on the website's server.

Whenever you do something on the website, like clicking a link or submitting a form, your web browser sends the session ID along with the request to the website's server. This tells the server that it's you who is making the request.

The server then checks its database to see if it has a record of your session ID. If it does, it retrieves any information associated with your session ID, like your username, preferences, or other account details. This information is used to customize the website for you, such as displaying your name at the top of the page or showing you content that's relevant to your interests.

If the server doesn't find your session ID in its database, it assumes that you're not logged in and may redirect you to a login page or restrict your access to certain parts of the website.

To make this process easier, many websites use cookies, which are small text files stored on your computer. When you log in to a website, the website may send a cookie to your browser that contains your session ID. Your browser then sends this cookie back to the website's server with each subsequent request, so the server knows it's you without having to check its database every time.

Overall, the use of session IDs and cookies allows a website to identify who is logged in and provide personalized content and functionality to each user.



