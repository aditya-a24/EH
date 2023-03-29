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






# The Internet Vs The Web

- The internet = the global connection of devices over TCP/IP
- TCP/IP = The networking protocol the internet uses
- HTTP = A service that uses TCP/IP to interact and display websites
- Request = A structured piece of text that is sent to a HTTP server
- Response = The reply to a request that your web browser renders as pretty pictures




# DNS

- We don't usually use IP addresses to access websites though
	- Instead we use their domain name
	- Domain names e.g. google.com - human friendly
	- Sometimes different domains go to different IPs
- But fundamentally we're using TCP/IP so we need an IP address
- DNS provides the bridge between domain name and IP
- Basically big phone books



![image](https://user-images.githubusercontent.com/60404663/228424113-e108bee0-24c3-4db8-9ae4-625a2edcd386.png)

# Q. How DNS Works?

- DNS (Domain Name System) is a hierarchical decentralized naming system for computers, services, or other resources connected to the Internet or a private network. DNS is used to translate human-readable domain names, like www.example.com, into machine readable IP addresses, like 192.0.2.1.

- Here's how DNS works:

1. You type a website address (URL) into your web browser.

2. Your computer sends a DNS query to a DNS resolver, which is typically provided by your Internet Service Provider (ISP).

3. If the resolver has the IP address of the website in its cache memory, it returns the IP address to your computer.

4. If the resolver does not have the IP address in its cache, it sends a query to the root DNS servers.

5. The root DNS servers respond with the IP address of the Top-Level Domain (TLD) server, which is responsible for the domain name extension, like .com, .org, or .net.

6. The resolver then sends a query to the TLD server, which responds with the IP address of the authoritative DNS server for the domain name.

7. The resolver sends a query to the authoritative DNS server, which responds with the IP address of the website.

8. The resolver caches the IP address and returns it to your computer.

9. Your computer uses the IP address to connect to the website's server and retrieve the website's content.

This entire process happens in a fraction of a second, and allows you to access any website on the Internet just by typing its domain name into your web browser.








# DNS Queries

- When a user wants to access insiderphd.dev
	- We work backwards
- First the request is sent to a recursive resolver owned by your ISP
	- But we need to find an authoritative name server
- The first step is finding the root name server, this will know TLDs.com/.net/ .dev
- At the .dev TLD(Top Level Domain) name server we can then look up insiderphd.dev
- We're then directed to the authoritative name server which for us is dns1.namecheaphosting.com


# Q. what is DNS query?

- A DNS query is a request for information sent from a client computer to a DNS server. DNS queries are used to resolve domain names to IP addresses, and they are a fundamental part of how the Internet works.

- When you enter a website address (URL) into your web browser, your computer sends a DNS query to a DNS resolver to obtain the IP address of the website. The DNS resolver will then process the query and return the IP address back to your computer so that your browser can connect to the website.

- A DNS query consists of several parts:

1. The domain name that needs to be resolved
2. The record type being requested (e.g., A, AAAA, MX, CNAME, etc.)
3. The class of the query (usually IN for Internet)
4. The query type (usually recursive or iterative)
5. The identifier for the query, which is used to match up the query with the response

- DNS queries can be recursive or iterative. In a recursive query, the DNS server will continue to query other DNS servers on behalf of the client until it obtains the requested information. In an iterative query, the DNS server will only provide the best information it has at the time and leave it up to the client to continue querying until it gets the desired result.

- DNS queries are a critical part of the Internet's infrastructure, and they enable users to access websites and other online resources quickly and reliably.


![image](https://user-images.githubusercontent.com/60404663/228424428-51d83414-428a-4cb8-9845-d9d39d04cd92.png)

# DNS Records
- A = IP address (IPv4 255.255.255.255)
- AAA = IP address (IPv6)
- CNAME = Alias to another domain name
- MX = Email
- NS = The name servers for the domain name
- PTR = Reverse IP look up
- TXT = Allows you to put anything in there
- SOA = Information about the domain's authority


# Q. what is root DNS servers?

- The root DNS servers are a group of authoritative DNS servers that are responsible for the root zone of the Domain Name System (DNS). The root zone is the top level of the DNS hierarchy, and it contains information about the top-level domain (TLD) nameservers, such as .com, .org, .net, etc.

There are 13 root DNS servers distributed across the world, each with its own unique IP address. These servers are maintained by different organizations and are located in different geographical locations to ensure redundancy and reliability of the DNS system.

When a DNS resolver receives a query for a domain name that it does not have in its cache, it sends a query to one of the root DNS servers to obtain the IP address of the authoritative DNS server for the domain name's TLD. The root DNS server responds to the query with the IP address of the TLD nameserver, which the resolver then contacts to obtain the IP address of the authoritative DNS server for the domain name.

The root DNS servers play a critical role in the functioning of the Internet's DNS system. Without them, the DNS system would not be able to resolve domain names to IP addresses, and users would not be able to access websites and other online resources using domain names.


# Q. what is TLD nameserver?

- A TLD nameserver is a type of authoritative DNS server that is responsible for maintaining information about the top-level domain (TLD) of the Domain Name System (DNS). TLD nameservers are responsible for handling DNS queries related to domain names that end with their respective TLDs, such as .com, .org, .net, etc.

There are multiple TLD nameservers for each TLD, and they are distributed around the world to ensure redundancy and reliability of the DNS system. The TLD nameservers are operated by the respective organizations that manage the TLDs.

When a DNS resolver receives a query for a domain name, it first contacts one of the root DNS servers to obtain the IP address of the TLD nameserver for the domain name's TLD. The resolver then sends a query to the TLD nameserver to obtain the IP address of the authoritative DNS server for the domain name.

For example, if a user types "www.example.com" into their web browser, the DNS resolver will first contact one of the root DNS servers to obtain the IP address of the .com TLD nameserver. The resolver will then contact the .com TLD nameserver to obtain the IP address of the authoritative DNS server for the "example.com" domain name. The authoritative DNS server will then return the IP address of the website to the resolver, which can then connect to the website's server to retrieve the website's content.

Overall, TLD nameservers play a critical role in the functioning of the DNS system, allowing users to access websites and other online resources using domain names.


# Q. what is authoritative DNS server?

- An authoritative DNS server is a type of DNS server that is responsible for storing and providing authoritative information about a specific domain name or set of domain names. When a DNS resolver needs to resolve a domain name to an IP address, it sends a query to the authoritative DNS server for the domain name to obtain the necessary information.

An authoritative DNS server is responsible for providing answers to DNS queries that relate to the domain names it is authoritative for. It has the final say in resolving DNS queries for those domain names, and its responses are considered to be definitive.

There are two types of authoritative DNS servers:

1. Primary authoritative DNS server: The primary authoritative DNS server is responsible for storing the original copy of the DNS zone file for a domain name. It is the only server that can make changes to the zone file, and it transfers updates to secondary DNS servers.

2. Secondary authoritative DNS server: The secondary authoritative DNS server is a backup server that receives updates to the DNS zone file from the primary authoritative DNS server. It is responsible for responding to DNS queries in the event that the primary authoritative DNS server becomes unavailable.

Authoritative DNS servers play a critical role in the functioning of the DNS system. They provide the necessary information to DNS resolvers to enable users to access websites and other online resources using domain names.




![image](https://user-images.githubusercontent.com/60404663/228430856-653fb09e-8a20-4960-99ae-66316a373953.png)

# Cookies and Sessions

- Sessions are stored on the server cookies are stored in your browser
- Sessions are deleted on web browser close
- Cookies can be stored for a long time
- Log in uses sessions, remember me adds a login cookie
	- Those cookies then start a new session
