# Understanding the difference between Load Balancer, API Gateway and the Reverse Proxy

![Untitled](https://raw.githubusercontent.com/akhilesh-k/blog-content/main/markdown/understanding-the-difference-between-load-balancer/cover.png)

## Background

For someone who has just began their software engineering career, Load balancers, API gateways, Reverse Proxy can seem similar and they might struggle to understand the difference between them. Load Balancer, API Gateway, and Reverse Proxy are essential components in distributed systems that play distinct roles in improving system performance, security, and manageability and are vital to the web services infrastructure. These components help in managing secure and scalable web application.

Let's use the analogy of a bustling restaurant to explain the concepts of Load Balancer, API Gateway, and Reverse Proxy working together in a distributed system:

1. **Load Balancer: The Greeter at the Door**
    
    Think of the load balancer as the greeter at the restaurant's entrance. As customers arrive the greeter ensures the table occupancy in the restaurant remains balanced by directing the to available tables, making sure no single area gets overcrowded. Similarly, in a distributed system, a load balancer evenly distributes incoming requests among various servers, preventing any one server from becoming overwhelmed.
    
2. **API Gateway: The Menu and Host**
    
    Imagine the API gateway as both the menu and the host at the restaurant. This menu simplifies the ordering process for customers. 
    
    In the same way, the API gateway provides the access different services in a distributed system to clients. It provides a clear menu of available services (APIs), ensures authentication, rate limiting, and routes the request to the right microservice.
    
3. **Reverse Proxy: The Waiter Serving Your Table**
    
    Now, imagine the reverse proxy as the waiter serving your table. You place your order with the waiter, who then goes to the kitchen, retrieves your food, and brings it back to your table. The waiter masks off the operations happening inside the kitchen. 
    
    Similarly, a reverse proxy, sits between clients and servers and handles requests on behalf of the servers. It acts as an intermediary for client requests, forwarding them to the appropriate server and returning the server's response to the client. Reverse proxies provide benefits such as caching, SSL termination, and improved security by shielding servers from direct exposure to the internet.
    

Now that we have a high level understanding from the analogy. Lets start delving deeper into these concepts.

## Load balancers

In a distributed system, especially when dealing with high traffic, a load balancer is crucial to evenly distribute incoming requests across multiple servers. This distribution prevents any single server from being overwhelmed, ensuring optimal utilisation of resources, enhancing response times, and improving the overall system's availability and scalability. 

![Load Balancer](https://raw.githubusercontent.com/akhilesh-k/blog-content/main/markdown/understanding-the-difference-between-load-balancer/load-balancer.png)

Load balancers can operate at different layers of the [OSI model](https://en.wikipedia.org/wiki/OSI_model)[1], including application, transport, and network layers. They can also perform health checks on servers and route traffic only to healthy instances. These are mainly working on two different layers:

**Transport Layer (Layer 4 in the OSI model)**

[Layer 4 load balancers](https://en.wikipedia.org/wiki/Multilayer_switch#Layer_4_load_balancer)[2] work at the transport layer, making decisions based on network-level information such as IP addresses and TCP/UDP ports. 

**Application Layer (Layer 7 in the OSI model)**

Layer 7 load balancers operate at the application layer, leveraging HTTP headers, cookies, and URL paths to make more granular decisions.

### Load Balancing Algorithms

Load balancing algorithms powers up how the load balancers distribute traffic. There are various algorithms which caters to the use cases. Here are few load balancing algorithms:

1. **Round Robin**: Cycles through the available servers and sequentially assigns requests.
2. **Least Connections**: Directs requests to the server with the fewest active connections.
3. **Weighted Round Robin**: Considers server capacities, distributing requests proportionally.
4. **Weighted Least Connections**: Balances load based on active connections and capacities.
5. **IP Hash**: Routes requests based on source/destination IP, maintaining session persistence.
6. **Least Response Time**: Sends requests to the server with the lowest response time.
7. **Least Bandwidth**: Routes to the server using the least network bandwidth.

## API Gateway

An API Gateway acts as a single entry point for clients (such as web or mobile applications) to access various services within a microservices architecture. 

![API Gateway](https://raw.githubusercontent.com/akhilesh-k/blog-content/main/markdown/understanding-the-difference-between-load-balancer/api-gateway.png)

It provides several important functions:

- **API Aggregation:** It aggregates requests from clients and routes them to the respective microservices, simplifying client-side communication.
- **Authentication and Authorization:** The API Gateway can handle authentication and authorization, ensuring that only authorized clients can access specific services.
- **Rate Limiting:** It can enforce rate limiting to prevent abuse or excessive usage of services by a single client.
- **Request Transformation:** The API Gateway can transform requests or responses to match the expected format of the client or service.
- **Logging and Monitoring:** It centralizes logging and monitoring of API traffic, making it easier to track usage and diagnose issues.

## Reverse Proxy

A reverse proxy is a server that sits between clients and servers, intercepting requests from clients and forwarding them to the appropriate server. 

![Reverse Proxy](https://raw.githubusercontent.com/akhilesh-k/blog-content/main/markdown/understanding-the-difference-between-load-balancer/reverse-proxy.png)

It offers several benefits:

- **Security:** A reverse proxy can act as a security layer, shielding the server information from external world and filtering out malicious requests.
- **Caching:** It can cache responses from servers, reducing the load on backend services and improving response times for frequently accessed resources.
- **SSL Termination:** The reverse proxy can handle SSL encryption and decryption, offloading this resource-intensive task from backend servers.
- **Content Compression:** It can compress and optimize content before delivering it to clients, saving bandwidth and improving performance.

## Popular tools for each components

Keeping it short and simple, here are few tools which I have personally used at some point of time.

1. **Load Balancers:** HAProxy, Ngnix, Traefik, Amazon ELB
2. **API Gatway:** Kong
3. **Reverse Proxies:** Ngnix, Apache HTTP Server, Cloudflare

In conclusion, these components are a must have for maintaining a scalable web infrastructure. The combinations of how you want to use the components depends upon your use cases.

Ref:

1. OSI Model: [https://en.wikipedia.org/wiki/OSI_model](https://en.wikipedia.org/wiki/OSI_model)
2. Layer 4 Load balancer: [https://en.wikipedia.org/wiki/Multilayer_switch#Layer_4_load_balancer](https://en.wikipedia.org/wiki/Multilayer_switch#Layer_4_load_balancer)