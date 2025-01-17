# What Happens When You Type google.com and Press Enter

## The Magical Journey of a Google Search

![What Happens When You Type google.com and Press Enter](https://cdn.hashnode.com/res/hashnode/image/upload/v1694681234567/your-image-url)

## Table of Contents

1. [Introduction](#introduction)
2. [DNS Request: Translating Domain Names into IP Addresses](#dns-request-translating-domain-names-into-ip-addresses)
3. [TCP/IP: The Foundation of Internet Communication](#tcpip-the-foundation-of-internet-communication)
4. [Firewall: The Digital Gatekeeper](#firewall-the-digital-gatekeeper)
5. [HTTPS/SSL: Secure Data Transmission](#httpsssl-secure-data-transmission)
6. [Load Balancer: Distributing the Workload](#load-balancer-distributing-the-workload)
7. [Web Server: Serving Up Web Pages](#web-server-serving-up-web-pages)
8. [Application Server: Handling Dynamic Content](#application-server-handling-dynamic-content)
9. [Database: Storing and Retrieving Data](#database-storing-and-retrieving-data)
10. [TL;DR](#tldr)
11. [Conclusion](#conclusion)
12. [Sources](#sources)

## Introduction

We've all done it countless times—opened our web browsers, typed "google.com" into the address bar, and hit Enter. Almost instantaneously, the Google search page appears like magic. But have you ever wondered what happens behind the scenes? In this article, we'll take you on a fascinating journey through the various steps and technologies involved in making that simple act a reality. Buckle up as we delve into DNS requests, TCP/IP, firewalls, HTTPS/SSL, load balancers, web servers, application servers, and databases.

## 1. DNS Request: Translating Domain Names into IP Addresses

Our journey begins with the Domain Name System (DNS). On the internet, computers identify each other with unique numbers called IP addresses. Computers don't understand human languages, and this is where DNS comes in. Think of DNS like the phonebook of the internet; its primary purpose is to translate human-readable domain names like "google.com" into the numerical IP addresses that computers use to identify each other.

When you type a web address like "google.com" into your browser's address bar and press Enter, your computer needs the IP address of the server hosting Google's website to establish a connection.

First, your computer checks its local DNS cache. This cache stores recently resolved domain names and their corresponding IP addresses. If "google.com" is in the cache, your computer can skip the rest of the DNS process, saving time and resources. However, if the IP address isn't in the cache, your computer sends a DNS request to the DNS server. This request translates the human-readable domain name (google.com) into the numerical IP address (e.g., 172.217.3.110) of the server hosting Google's website.

![DNS Request](https://cdn.hashnode.com/res/hashnode/image/upload/v1694718540857/36791708-d0f7-4563-8489-42f683a5e99e.png?auto=compress,format&format=webp)

## 2. TCP/IP: The Foundation of Internet Communication

With the IP address in hand, your computer initiates a connection to the Google server using the Transmission Control Protocol (TCP) over the Internet Protocol (IP), collectively known as TCP/IP. This robust communication protocol ensures data reliability and integrity during transmission.

TCP/IP is the fundamental set of communication protocols that govern how data is transmitted and received across the internet. It's the backbone of internet communication, ensuring reliable and orderly data exchange between devices and networks.

The primary role of TCP is to provide reliable, connection-oriented communication. When your computer and a web server want to communicate over the internet, they initiate a TCP connection. This process involves a three-way handshake that ensures both devices agree to establish a connection:

- The client sends a "SYN" (synchronize) packet to the server.
- The server responds with a "SYN-ACK" (synchronize-acknowledge) packet.
- The client acknowledges with an "ACK" packet.

Once the connection is established, TCP ensures data is sent reliably and in the correct order, managing the flow of data between sender and receiver to prevent data overload by implementing congestion control mechanisms.

When data exchange is complete, both devices engage in a graceful connection termination, which involves a four-way handshake:

- The client sends a "FIN" (finish) packet to the server.
- The server acknowledges with an "ACK" packet.
- The server then sends its "FIN" packet.
- The client acknowledges the server's "FIN" with an "ACK."

The primary role of IP is to handle the routing and addressing of data packets across networks. Data is divided into small packets for transmission. Each packet is tagged with a source and destination IP address, allowing routers to determine where to send the packets. Routers use the destination IP address to determine the best path for each packet to reach its destination.

![TCP/IP Communication](https://cdn.hashnode.com/res/hashnode/image/upload/v1694723348645/00acffc2-7698-407d-bb8b-11c40de915d4.png?auto=compress,format&format=webp)

## 3. Firewall: The Digital Gatekeeper

As your data packets traverse the internet, they encounter firewalls—security systems designed to monitor and control incoming and outgoing network traffic based on predetermined security rules. Firewalls act as digital gatekeepers, protecting your computer and network from unauthorized access and potential threats.

Firewalls can be hardware-based, software-based, or a combination of both. They establish a barrier between trusted internal networks and untrusted external networks, such as the internet. By analyzing data packets, firewalls determine whether to allow or block specific traffic based on security rules.

![Firewall Security](https://cdn.hashnode.com/res/hashnode/image/upload/v1694726332768/fcafd247-9d6a-4ca8-b075-7f0ad922844a.jpeg?auto=compress,format&format=webp)

## 4. HTTPS/SSL: Secure Data Transmission

When accessing "google.com," your browser uses Hypertext Transfer Protocol Secure (HTTPS), an extension of HTTP that provides secure communication over a computer network. HTTPS ensures that data transmitted between your browser and the web server is encrypted, protecting it from eavesdroppers and man-in-the-middle attacks.

HTTPS relies on the Secure Sockets Layer (SSL) or its successor, Transport Layer Security (TLS), to encrypt the data exchanged between your browser and the server. This encryption ensures that even if data is intercepted, it cannot be read without the decryption key.

![HTTPS SSL Encryption](https://cdn.hashnode.com/res/hashnode/image/upload/v1694726958950/d93b312f-55e3-4f62-b545-e7c926c3f025.jpeg?auto=compress,format&format=webp)

## 5. Load Balancer: Distributing the Workload

Upon reaching Google's infrastructure, your request is directed to a load balancer. A load balancer distributes incoming network traffic across multiple servers, ensuring no single server becomes overwhelmed. This distribution optimizes resource use, maximizes throughput, minimizes response time, and ensures reliability.

Load balancers use various algorithms to determine how to distribute traffic, such as round-robin, least connections, or IP hash. By balancing the load, they prevent server overload and contribute to a seamless user experience.

![Load Balancer](https://cdn.hashnode.com/res/hashnode/image/upload/v1694727731572/2d170f01-8f00-4e9e-9c74-58b365e99445.jpeg?auto=compress,format&format=webp)

## 6. Load Balancer: Distributing the Workload

Upon reaching Google's infrastructure, your request is directed to a load balancer. A load balancer distributes incoming network traffic across multiple servers, ensuring no single server becomes overwhelmed. This distribution optimizes resource use, maximizes throughput, minimizes response time, and ensures reliability.

Load balancers use various algorithms to determine how to distribute traffic, such as round-robin, least connections, or IP hash. By balancing the load, they prevent server overload and contribute to a seamless user experience.

![Load Balancer](https://cdn.hashnode.com/res/hashnode/image/upload/v1694728529523/315c2371-c3d4-44b4-910d-5464788de970.jpeg?auto=compress,format&format=webp)

## 7. Web Server: Serving Up Web Pages

The web server—in this case, something like Nginx or Apache—is responsible for serving static files (such as images, CSS, and JavaScript) and processing requests for dynamic content by forwarding them to the application server. It acts as the intermediary between the client and the backend services, ensuring that the appropriate resources are delivered.

Web servers also handle caching, logging, and sometimes SSL termination to reduce the load on application servers.

![Web Server](https://cdn.hashnode.com/res/hashnode/image/upload/v1694728881100/4467dd45-a464-4371-abf9-6d71594e2909.png?auto=compress,format&format=webp)

## 8. Application Server: Handling Dynamic Content

Once a request for dynamic content reaches the application server, it processes the business logic and communicates with the database to retrieve or store data. The application server runs the core logic of the application, such as rendering personalized user experiences or processing form submissions.

For example, when you search for something on Google, the application server processes your query, retrieves relevant data from the database, and returns a dynamic response that is displayed in your browser.

![Application Server](https://cdn.hashnode.com/res/hashnode/image/upload/v1694729215315/0095732c-49d2-4301-bea7-092e346d43a4.png?auto=compress,format&format=webp)

## Conclusion

The journey from typing "google.com" to seeing the Google search page involves multiple interconnected technologies and processes. Understanding these components helps us appreciate the complexity and ingenuity of the internet.

## Sources

1. [How the Internet Works - MDN Web Docs](https://developer.mozilla.org/en-US/docs/Learn/Common_questions/How_does_the_Internet_work)
2. [What Happens When You Type a URL in a Browser? - GeeksforGeeks](https://www.geeksforgeeks.org/what-happens-when-you-type-a-url-in-browser/)
3. [Load Balancers - AWS Documentation](https://docs.aws.amazon.com/elasticloadbalancing/latest/userguide/how-elastic-load-balancing-works.html)
4. [Application Server vs Web Server - Colocation America](https://www.colocationamerica.com/blog/application-server-vs-web-server)
5. [What is TCP/IP? - AVG](https://www.avg.com/en/signal/what-is-tcp-ip)
6. [What is TCP/IP? - Avast](https://www.avast.com/c-what-is-tcp-ip)
7. [What Happens](https://sophiaintech.hashnode.dev/what-happens-when-you-type-googlecom-and-press-enter#heading-1-dns-request-translating-domain-names-into-ip-addresses)
8. [Stock Images - Adobe Stock](https://stock.adobe.com/)
9. [Firewall as a Service - Aimultiple Research](https://research.aimultiple.com/firewall-as-a-service/)
10. [Discussion Forums - FreeCodeCamp](https://forum.freecodecamp.org)
11. [YouTube Playlist - Networking Concepts](https://youtube.com/playlist?list=PLBbU9-SUUCwUyqvfypPAHWOaDr7Wz4P6t&si=eLZITu6i6H7BJsqq)