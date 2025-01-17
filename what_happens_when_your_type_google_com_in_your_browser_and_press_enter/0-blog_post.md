# What Happens When You Type google.com and Press Enter

## Table of Contents

1. [Introduction](#introduction)
2. [DNS Request: Translating Domain Names into IP Addresses](#2-dns-request-translating-domain-names-into-ip-addresses)
3. [TCP/IP: The Foundation of Internet Communication](#3-tcpip-the-foundation-of-internet-communication)
4. [Firewall: The Digital Gatekeeper](#4-firewall-the-digital-gatekeeper)
5. [HTTPS/SSL: Secure Data Transmission](#5-httpsssl-secure-data-transmission)
6. [Load Balancer: Distributing the Workload](#6-load-balancer-distributing-the-workload)
7. [Web Server: Serving Up Web Pages](#7-web-server-serving-up-web-pages)
8. [Application Server: Handling Dynamic Content](#8-application-server-handling-dynamic-content)
9. [Database: Storing and Retrieving Data](#9-database-storing-and-retrieving-data)
10. [TL;DR](#tldr)
11. [Conclusion](#conclusion)
12. [Sources](#sources)

## Introduction

We've all done it countless times—opened our web browsers, typed "google.com" into the address bar, and hit Enter. Almost instantaneously, the Google search page appears like magic. But have you ever wondered what happens behind the scenes? In this article, we'll take you on a fascinating journey through the various steps and technologies involved in making that simple act a reality. Buckle up as we delve into DNS requests, TCP/IP, firewalls, HTTPS/SSL, load balancers, web servers, application servers, and databases.

## 2. DNS Request: Translating Domain Names into IP Addresses

Our journey begins with the Domain Name System (DNS). On the internet, computers identify each other with unique numbers called IP addresses. Computers don't understand human languages, and this is where DNS comes in. Think of DNS like the phonebook of the internet; its primary purpose is to translate human-readable domain names like "google.com" into the numerical IP addresses that computers use to identify each other.

When you type a web address like "google.com" into your browser's address bar and press Enter, your computer needs the IP address of the server hosting Google's website to establish a connection.

First, your computer checks its local DNS cache. This cache stores recently resolved domain names and their corresponding IP addresses. If "google.com" is in the cache, your computer can skip the rest of the DNS process, saving time and resources. However, if the IP address isn't in the cache, your computer sends a DNS request to the DNS server. This request translates the human-readable domain name (google.com) into the numerical IP address (e.g., 172.217.3.110) of the server hosting Google's website.

![DNS Request](https://cdn.hashnode.com/res/hashnode/image/upload/v1694718540857/36791708-d0f7-4563-8489-42f683a5e99e.png?auto=compress,format&format=webp)

## 3. TCP/IP: The Foundation of Internet Communication

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

## 4. Firewall: The Digital Gatekeeper

Before your computer establishes a connection with the Google server, it may encounter a firewall. Firewalls act as digital gatekeepers, monitoring incoming and outgoing traffic for security threats. They allow legitimate requests to pass while blocking suspicious or malicious traffic.

A firewall is a network security device or software application that inspects and manages the flow of network traffic, both incoming and outgoing, based on a set of predefined security rules. Its primary goal is to enforce a security policy and prevent unauthorized or potentially harmful data packets from entering or leaving a network.

If your incoming request meets the security rules set by the firewall in front of Google's server, it is allowed through, and the browser is able to access the website.

![Firewall Security](https://cdn.hashnode.com/res/hashnode/image/upload/v1694726332768/fcafd247-9d6a-4ca8-b075-7f0ad922844a.jpeg?auto=compress,format&format=webp)

## 5. HTTPS/SSL: Secure Data Transmission

To secure your data during transit, websites like Google use HTTPS (Hypertext Transfer Protocol Secure) with SSL (Secure Sockets Layer) or its successor, TLS (Transport Layer Security). This encryption ensures that the data exchanged between your browser and the server remains confidential and tamper-proof.

HTTPS/SSL works through a process called encryption, which scrambles the data transmitted between your browser and the web server. When you connect to a website over HTTPS, your browser and the web server engage in a "handshake." During this process, they agree on encryption methods and exchange cryptographic keys. This ensures that both parties can understand and decode the data being transmitted.

Once the handshake is complete, all data exchanged between your browser and the web server is encrypted. This means that even if someone intercepts the data during transmission, they won't be able to understand it without the decryption keys

SSL/TLS not only encrypts data but also ensures its integrity. This means that the data cannot be altered during transit without detection. If someone tries to tamper with the data, it will be rendered unreadable. When you visit a website with a valid SSL certificate, you can be reasonably sure that you are connecting to a genuine server and not a malicious imposter.

![HTTPS SSL Encryption](https://cdn.hashnode.com/res/hashnode/image/upload/v1694726958950/d93b312f-55e3-4f62-b545-e7c926c3f025.jpeg?auto=compress,format&format=webp)

## 6. Load Balancer: Distributing the Workload

Behind the scenes, Google's infrastructure is vast and distributed across multiple servers because it receives billions of website visitors a day. This is where load balancers come into play to evenly distribute user requests among these servers to ensure that no single server is overwhelmed, maintaining optimal website performance.

A load balancer is a network device or software application that acts as an intermediary between client devices (such as web browsers) and a group of backend servers. Its primary purpose is to:

- **Distribute incoming network traffic** or application requests across multiple servers.

- **Enhance scalability** to handle varying levels of traffic. This scalability is crucial for handling sudden traffic spikes without service degradation.

- **Improve Availability** through continuous monitoring. If a server becomes unresponsive or fails, the load balancer can automatically redirect traffic to healthy servers, minimizing downtime and improving service availability.

![Load Balancer](https://cdn.hashnode.com/res/hashnode/image/upload/v1694727731572/2d170f01-8f00-4e9e-9c74-58b365e99445.jpeg?auto=compress,format&format=webp)

## 7. Web Server: Serving Up Web Pages

Once your request reaches the web server, it retrieves the requested web page, such as the Google homepage. Web servers, like Apache or Nginx, handle HTTP requests, process server-side scripting, and serve static content to your browser.

A web server is a specialized software or hardware component designed to handle incoming HTTP (Hypertext Transfer Protocol) requests from client devices and respond by delivering web content.

When you request a web page, such as 'google.com,' your browser's request is first received by a load balancer, which directs it to one of many web servers. The web server processes the request, generating a response that includes essential page components like HTML, CSS, and JavaScript. This response is then sent back through the load balancer to your browser, which renders the web page using the received components, resulting in the familiar web page display.

![Load Balancer](https://cdn.hashnode.com/res/hashnode/image/upload/v1694728529523/315c2371-c3d4-44b4-910d-5464788de970.jpeg?auto=compress,format&format=webp)

## 8. Application Server: Handling Dynamic Content

In addition to static web pages, websites often contain dynamic content, like search results on Google. Application servers, like those running Python, Ruby, or Node.js, handle these dynamic requests, querying databases and generating personalized content.

![Web Server](https://cdn.hashnode.com/res/hashnode/image/upload/v1694728881100/4467dd45-a464-4371-abf9-6d71594e2909.png?auto=compress,format&format=webp)

## 9. Database: Storing and Retrieving Data

Behind the scenes, Google relies on massive databases to store and retrieve information quickly. When you perform a search, the application server queries these databases to fetch the most relevant results, which are then presented to you.

A database is a collection of data, and the DBMS is the program that is going to interact with the database and retrieve, add, and modify data in it.

![Application Server](https://cdn.hashnode.com/res/hashnode/image/upload/v1694729215315/0095732c-49d2-4301-bea7-092e346d43a4.png?auto=compress,format&format=webp)

## TL:DR

When you type "google.com" in your browser and press enter, a request is sent to the DNS server that translates human-friendly domain names into computer-friendly IP addresses. Then, TCP/IP, the internet's communication foundation, ensures reliable data exchange with its 3-way and 4-way handshakes. Firewalls act as digital gatekeepers, allowing secure traffic and blocking threats. HTTPS/SSL encrypts data, ensuring confidentiality and integrity. Load balancers evenly distribute traffic to maintain optimal website performance. Web servers serve up web pages, handling HTTP requests and processing scripts, while application servers manage dynamic content like search results. Behind the scenes, massive databases store and retrieve data quickly.

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