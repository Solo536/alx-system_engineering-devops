#  Secured and monitored web infrastructure

<img src="2-secured_and_monitored_web_infrastructure.png" alt="Secured and monitored web infrastructure image">

A three server web infrastructure that hosts the website www.foobar.com, is secured, serves encrypted traffic, and is monitored, we will add:

### Three firewalls:
We are adding firewalls to the infrastructure to provide security by controlling and monitoring incoming and outgoing traffic.

### SSL Certificate
An SSL certificate to serve www.foobar.com over HTTPS: We are adding an SSL certificate to encrypt the traffic between the server and the user, providing secure communication.

### Three monitoring clients:
We are adding monitoring clients to the infrastructure to monitor the health and performance of the servers and applications, detect issues and troubleshoot them before they impact the users.

## Specifics about this infrastructure:

### Firewalls:
Firewalls are network security systems that monitor and control incoming and outgoing traffic based on predefined security rules. They provide protection against malicious attacks, unauthorized access, and data theft.

### HTTPS:
HTTPS (Hyper Text Transfer Protocol Secure) is a protocol used to secure communication over the internet by encrypting the traffic between the server and the user. HTTPS uses SSL/TLS certificates to establish a secure connection between the client and the server.

### Monitoring:
Monitoring is the process of collecting and analyzing data from various sources to ensure the health and performance of the infrastructure, applications, and services. It helps detect issues, troubleshoot them, and prevent downtime and data loss.

#### Monitoring tool:
The monitoring tool used should be capable of collecting data from various sources, such as logs, metrics, and events. It should also provide visualization, alerting, and analysis capabilities to help administrators detect issues and troubleshoot them.

#### Monitoring QPS: 
To monitor the web server QPS (Queries Per Second), we can use monitoring tools like Prometheus or Grafana that collect metrics data and visualize it in dashboards. We can set up alerts to notify administrators when QPS exceeds a certain threshold.

## Issues with this infrastructure:

Terminating SSL at the load balancer level can be an issue as it can expose sensitive data to potential attacks. It is recommended to use end-to-end encryption with SSL certificates at the web server level.

Having only one MySQL server capable of accepting writes can be an issue as it can lead to a single point of failure. It is recommended to set up a MySQL cluster with Primary-Replica (Master-Slave) nodes to ensure high availability and data redundancy.

Having servers with all the same components (database, web server, and application server) can be a problem as it can lead to a single point of failure. It is recommended to use load balancers and multiple servers to ensure high availability and redundancy.
