# Distributed web infrastructure

<img src="1-distributed_web_infrastructure.png" alt="Simple web stack image">

A three-server web infrastructure that hosts the website www.foobar.com, we would need to add two servers to the existing setup. The following are the details of the infrastructure:

### Web Server:
The web server (Nginx) is responsible for serving static content and handling HTTP requests from the users. It listens for incoming requests and routes them to the appropriate application server.

### Application Server:
The application server is responsible for handling dynamic content and running the codebase. It receives requests from the web server, processes them, and sends the response back to the web server.

### Load Balancer:
The load balancer (HAproxy) is responsible for distributing incoming requests evenly across the two application servers. It is configured with a round-robin distribution algorithm, which works by sending each request to the next available server in a circular order.

### Database:
The database (MySQL) stores and retrieves data for the application. It is configured with a Primary-Replica (Master-Slave) cluster, which works by having one Primary node that accepts read-write requests and one or more Replica nodes that accept read-only requests. The Primary node is responsible for handling all write requests and synchronizing the data with the Replica nodes.

### Application Files:
This contains the codebase for the application that is being hosted.

The load balancer to distribute incoming traffic across multiple application servers, improving performance and reducing the chances of downtime due to a single point of failure (SPOF). The load balancer is configured with a round-robin algorithm to evenly distribute the traffic.

### Active-Active or Active-Passive setup
The load balancer is enabling an Active-Active setup, where both application servers are active and can handle incoming traffic. In contrast, an Active-Passive setup would have one server as the primary server and the other server as the backup. In case the primary server fails, the backup server would take over. However, this can result in lower performance as only one server is active at a time.

### Primary-Replica (Master-Slave)
The database Primary-Replica (Master-Slave) cluster works by having the Primary node accept read-write requests and synchronize the data with the Replica nodes. The Replica nodes can handle read-only requests and provide redundancy in case the Primary node fails. However, there can be a delay in data replication between the Primary and Replica nodes, leading to potential data consistency issues.

The Primary node in the database cluster is responsible for handling all write requests and synchronizing the data with the Replica nodes. In contrast, the Replica nodes can only handle read-only requests and do not have the capability to make changes to the data. As a result, the Primary node is critical to the functioning of the application.

### Issues with this infrastructure
The issues with this infrastructure include the presence of SPOF, as the load balancer and database Primary node can become a single point of failure. Security issues can also arise due to the lack of a firewall and HTTPS implementation. Additionally, there is no monitoring in place to ensure that the infrastructure is functioning correctly and to detect and address any issues that arise.
