# Simple web stack

<img src="0-simple_web_stack.png" alt="Simple web stack image">

## About
First, let's start with a user wanting to access the website hosted on this infrastructure. When a user types www.foobar.com in their web browser, their computer sends a request to the domain name system (DNS) server to resolve the domain name into an IP address. The DNS server then returns the IP address of the server that is hosting the website.

In this case, the DNS server returns the IP address 8.8.8.8, which is the IP address of our server. The user's computer then establishes a connection with the server using HTTP protocol to request the website content.

## components of the infrastructure:

### Server: 
A server is a computer that provides services or resources to other computers over a network. In this case, our server hosts the website content and serves it to users who request it.

### Domain name:
A domain name is a human-readable name that represents an IP address on the internet. It makes it easier for users to remember and access websites. In this case, the domain name is foobar.com, and it is configured with a www record that points to our server's IP address.

### DNS record:
The www record is a DNS record that is used to associate a domain name with a specific host or server. In this case, the www record is associated with our server's IP address, so when users type www.foobar.com, the DNS server returns our server's IP address.

### Web server:
A web server is a software that runs on the server and handles incoming HTTP requests from users' web browsers. In this infrastructure, we use Nginx as our web server.

### Application server:
An application server is a software that runs on the server and handles the application logic and business rules of a web application. In this infrastructure, we use gnu unicorn as our application server to execute our code base.

### Application files:
The application files are the code base of our web application that contains the logic and functionality of the website. In this infrastructure, the application files are stored on the server and executed by the application server.

### Database:
A database is a software that stores and manages data for web applications. In this infrastructure, we use MySQL as our database to store and manage our website data.

## Issues with this infrastructure:

### SPOF:
The infrastructure has a single point of failure (SPOF), which means that if the server goes down, the entire website becomes inaccessible.

### Downtime during maintenance:
Whenever we need to deploy new code or perform maintenance on the web server, we need to restart the web server, which results in downtime for the website.

### Scalability:
The infrastructure cannot scale if we receive a large amount of incoming traffic. As the traffic increases, the server will not be able to handle it, resulting in slow website performance or downtime.

To overcome these issues, we can consider adding more servers, load balancers, and other scaling techniques. We can also use caching mechanisms and content delivery networks (CDNs) to improve website performance and reduce server load.
