# HTTP protocol: （Hypertext Transfer Protocol）

一种访问协议，用于从server取得信息。It defines the way that clients interact with servers, i.e. transmit files such as HTML between clients and servers. 定义了servers and clients之间交流的方式。

- HTTP uses TCP (Transimission Contorl Protocol) to interact with clients.  
- HTTPS 是加密协议，https uses SSL， SSL是TCP的加强版，提供了安全性服务  

# Server: (服务器)

Simply a computer (server-side) that serves information to other computers (client-side).

# Proxy: (代理)

An intermediary role between clients and the server.

Two types of proxies: forward proxy and reverse proxy


# Internet & World Wide Web (the web):

The Web: is the pages we see when we are online, is the resources shared and transmitted via internet.

- Internet: a network of computers 1. connected together 2. share information and allow communication.
- Internet is formed with computers and cables.

# On-Premise Hosting

A company hosts everything in-house, i.e. you have own data centers and you own all the equipments, often find it difficult to scale up or down.

In comparison, there is off-premise hosting, often refers to cloud hosting.

Disadvantages:

	1. Overhead costs of hardware instances. Extra costs for industry compliance. (e.g. data protection, security issues)
	2. Virtual machine needs to provisioned for testing a new feature.
	3. Pay for all the infrastructure setup upfront
  
Less control over geographical latency.


# Host vs Server

Host: often refers to a company that owns a number of servers, and provides web hosting services to different clients.

Server: just one server that provides services to a particular client.

# Latency

The time it takes for request to be responded (server->browser and browser->server), depending on geographic distance.

# IP address vs Ports

- IP address: 
Like an identity of a computer in a network, it is unique. Considering it as your personal ID, or telephone number.

- Ports
A computer can have only 1 IP address but many port numbers. Each port number representing a service or application. So port number is used to distinguish at application level.

# AWS IP address & Port:

All AWS services interact with each other over TCP (Transmission Control Protocol) connections. Each service may use a different port.

Usually you initilise those connections within your application by making requests to the AWS services. 

You can create all your instances (data center, data server, host server?) in the same Virtual Private Cloud, then they can have local IP address which you can quickly access. 

# Credentials

The things you need to login to an account. At the very least, the credentials are username and password. 

In AWS, the credentials include access key and secret key.


# Gateway

A node (router) in a computer network, a key stopping point for data on its way to or from other networks


# API

A messenger that deliver clients' request to the server and then send the response back to clients. 
It does not include the functions that process the request under the hood.

It's like a Get function, but it's for external users to get what they want from your service.

# API Gateway

Like a door for an API. It is a management tool for API and it sits between clients and backend services. 

What it does: it accepts all API calls and fulfil them and return them. 

In microservice architecture, an API gateway often handles a request by invoking multiple microservices and aggregate the results.

# Routing & Router & Routing table

Routing means selecting the path in the network from one computer to the other (destination). 

Routers is a hardware (device) that is responsible for routing. It will decide which path to go and which one is faster. 

Routing table contains all the paths within the network for the router to make proper decisions. 

# SSH

It is used to log into a remote machine and execute commands.

# Serverless

Refers to using microservice architecture and Faas like lambda function in AWS.

So there are basically 3 ways to deploying your application:

1. Running it on your own hardware (on-premise)
2. Running it on your EC2 instances in the cloud

Running it completely serverless using lambda functions
