# WebChat

This is a Java based application that implements web-socket based real-time multi-use chat application using Spring Boot and RabbitMQ framework. The WebSocket protocol presents a method to enable your application to manage real-time communications. Other common options include long polling and server-sent events, each having their own benefits and drawbacks. This article will detail the steps to implement WebSockets utilizing the Spring Boot Framework, covering both the server-side and client-side setups. Communication between the two will utilize the STOMP over WebSocket protocol.

The server-side will be coded entirely in Java, while the client-side examples will showcase both Java and JavaScript (SockJS) code. This is because WebSockets clients are typically embedded within front-end applications. The code samples will illustrate how to publish messages to multiple users using the pub-sub model, as well as how to send messages to a single user. The article will also briefly touch on securing WebSockets and ensuring the solution remains functional even in non-WebSocket-supporting environments.

The WebSocket protocol permits two-way communication between applications. It's essential to recognize that HTTP only initiates the connection before it upgrades to a fresh TCP/IP connection exclusively for WebSocket use.

The WebSocket protocol functions as a low-level protocol that explains how a series of bytes becomes frames. These frames can include a text or binary message. As the message itself does not include additional routing or processing information, more intricate applications require supplementary coding. Luckily, the WebSocket specification permits the utilization of sub-protocols that function at a higher, application level. One of these is STOMP, supported by the Spring Framework.

STOMP is a straightforward text-based messaging protocol originally intended for scripting languages like Ruby, Python, and Perl to connect with enterprise message brokers. STOMP allows clients and brokers built in distinct languages to send and receive messages to each other. The WebSocket protocol is often referred to as "TCP for Web," while STOMP is referred to as "HTTP for Web." It defines a small set of frame types that are translated to WebSocket frames, such as CONNECT, SUBSCRIBE, UNSUBSCRIBE, ACK, or SEND. These commands simplify communication management and enable more sophisticated features such as message acknowledgment.

## Architecture

![alt_text](https://github.com/gitpushOmnik/WebChat/blob/main/workflow-arch.png)
