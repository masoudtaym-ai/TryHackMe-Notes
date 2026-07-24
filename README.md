# TryHackMe-Notes
All my self studies in tryhackme

# Intro to CyberSec

## Local Area Network (LAN) Topologies

learnt star topology

1. most commonly found today
2. most scalable
3. most expensive
4. requires high maintenance as scaling goes up

learnt bus topology

1. cheaper
2. easy to setup
3. slow due to using one pathway to send data
5. if one link breaks the rest follow due to it all being in one cable

learnt ring topology

1. similar to bus
2. no realince on an external device as all computers connect to eachother 27 3. no bottlenecks as it doesnt use a singe cable but connects all devices

did a practical test to understand the faulits and failure points of each topology

## Primer on Subenetting

Subnetting: Breaking a large network down into smaller, segmented pieces

Benifits:

Efficiency
1. reduces wasted cpu and bandwidth since it doesnt need to ping every device in the network
2. cleaner routing due to not needing to look at a massive list everytime

Security
1. Subnetting allows you to isolate differnet parts of an organization like employee and guest wifi being seperate to keep critical servers out of harm
2. If somoone in the guest network gets compromised critical servers wont get affected since it cant easily jump to another subnet
3. can create ACLs (Access Control Lists) to create rules for security

Control
1. can allocate more bandwidth depending on the need of each subnet
2. easier troubleshooting since pain points are more devided compraed to looking through the entire network

. Network Address is like the specific neighborhood block or street name of a network and tells where it is 
. Host Address is like the house number in this analogy telling where its located in the "neighborhood block:
. Default Gateway is like the entrance gate for this anology any data going in and out has to go to here to be directed to its intended location

## ARP Address Resolution Protocol

technology that is responsible for allowing devices to identify themselves on a network

An ARP connects a MAC address with its respected IP address
In order to map these two identifiers together, ARP sends two typs of messages

1. ARP Request
2. ARP Reply

a message is broadcasted on the network to other devices asking "what is the mac address that owns this IP ?" 
when other devices receive that message, only the owner of that IP address will send an ARP reply with its MAC address
after that the requesting device will now remember this mapping and store it in its ARP cache for future use

## DHCP Dynamic Host Configuration Protocol

automatically assigns a IP address to a computer

IP can also be physically inputted into a device but much more common to use DHCP

# Inside a Computer System

## Intro

Understanding physical parts of a computer

Passed a practical test about each component and what they do inside a computer system

<img width="1186" height="930" alt="image" src="https://github.com/user-attachments/assets/6a1d80d3-1bc1-4a35-b97d-775ec3bccfe1" />

## What happens when you boot up a computer? 

Step 1: Press the Power Button
When we press the power button on our computer system, a signal is sent to the PSU to allow power to flow

Step 2: Firmware starts
our core components are up and running, but our "brain" is not yet conscious. Like our bodies, a computer system contains firmware that allows all its components to start up. The central system that manages this is called the Unified Extensible Firmware Interface (UEFI)

Step 3: Power-On Self Test
Now that it is up and running, it is time to test if everything is functioning as it should. If something isn't, there will be some alarm signals. One of the routines that the UEFI loads is the Power-On Self Test, which tests if every required component is present, configured correctly, and functioning.

Step 4: Select Boot Device
system searches for the location of our bootup routine to start. the UEFI holds an ordered list which prioritizes on which device to look first for the boot up routine for the Operating System.

Step 5: Initiate Bootloader
initiates the "load routine" to start it. Our computer systems follow a similar process: On the selected boot device, the bootloader is initiated. This bootloader transfers the Operating System from the selected boot device to the Random Access Memory. Once the is transferred, the UEFI gives control over the different components to the OS.

Passed an exam to memorize all parts of the boot up sequence.
<img width="1174" height="1132" alt="image" src="https://github.com/user-attachments/assets/5548464a-358d-42af-9bf1-b623068795e7" />

# Computer Types

## Intro

learn the Ablity to identify and distinguish between different types of computers in use directly, such as laptops and smartphones, and indirectly, such as servers, devices, and embedded systems. will also understand what makes each type suited to its purpose.

<img width="965" height="417" alt="image" src="https://github.com/user-attachments/assets/9984bc67-2f10-42c3-ac7e-7d4014973ced" />

<img width="1487" height="386" alt="image" src="https://github.com/user-attachments/assets/553d628a-e437-490b-bc44-0c5cebbd4c5a" />

IOT vs Embedded: Both can be small and single-purpose. The difference is connectivity. IOT devices connect to a network to report data or receive commands. Embedded computers might not connect to anything; they do their job inside the machine, often for years without anyone knowing they exist.

completed an interactive challenge/exam about each type of computer its benefits and downsides and how they are different
<img width="1163" height="802" alt="image" src="https://github.com/user-attachments/assets/8b9748cc-1c41-48e3-9070-fbb4ea144e20" />

# Client-Server Basics

## Learning Objectives

Understand the Client-Server model
Understand the following concepts on a surface level:

  DNS
  Client
  Server
  Port
  Protocol
  Network

Service, Client, Server
there is a client that requests and a server that serves what it needs.
client is the one who always initiates the request.

Request and Response
we can say that a user used a browser (the client) to request a webpage from a server, which then sent the webpage to the client.

Protocol
Protocol which computer systems use to communicate. A protocol defines how a client can communicate with a server. This definition includes:

Which commands do the client and server understand. E.g., the get command.
How a request is structured. E.g., first the command and then the order.
What syntax is used. E.g., user uses the English language.
What response should be given to which type of request. E.g., a request for pizza results in receiving the available pizza.
What response to give to faulty requests. E.g., the server at Luigi's Pizzas says: No pepereonni pizza available

Port
A port is used to identify a specific service running on a system. When a client wants to access a service on a server, it must connect using the correct port.

DNS
DNS stands for Domain Name Service and works similarly to GPS: when you enter the name of, for example, a website, DNS resolves it to server's location. These location coordinates are called an Internet Protocol (IP) address in computer terms.

## Web Communication 

Hypertext Transfer Protocol (Secure), abbreviated as HTTP(S), is a stateless client-server protocol used for the World Wide Web.
This means that each request is processed independently, without the server retaining information about previous requests.

Although the protocol itself is stateless, modern websites and web applications implement mechanisms to introduce statefulness at the application level. (Cookies or token)

## HTTP Commands

 there are 9 core commands. In HTTP lingo, we use the term method instead of command. Below you can see an overview of these methods:
 
GET
POST
PUT
DELETE
PATCH
HEAD
OPTIONS
CONNECT
TRACE

Using a Virtual machine to learn each HTTP command and using real world examples passing each test.
<img width="1122" height="1272" alt="image" src="https://github.com/user-attachments/assets/142248da-e419-40a4-8a56-bdfe7302ec12" />
Scheme: Tells us which protocol was used: HTTP or HTTPS.
Host: Tells us the name of the host we request resources from.
Filename: Indicates which file we requested from the host. In our request, this is "/", which actually translates to "index.html".
Address: Displays the IP address where the website is hosted. In our example, we are hosting the website on the same device. That's why the address 127.0.0.1 is shown.
Status: This field indicates whether the request was successful. In our example, we received a "200 OK" status, which means that the request was successful.

# Virtualisation Basics

## Learning Objectives

  Understand why managing applications on individual physical servers is inefficient.
  Learn how virtualization addresses hardware utilization and scalability challenges.
  Understand the components of a lab machine.
  Learn how containers have further optimized hardware utilization for applications.

## Virtualization Overview 

In the early days, digital services were run on physical machines, and each machine typically had a single, clear purpose, such as hosting a website or storing data. As businesses added more services, they naturally increased the number of physical servers, and the “one job per box” approach became the standard for building reliable systems.

The problems were obvious:
High cost: Buying multiple physical servers is expensive, not just the hardware, but also electricity, cooling, maintenance, and data center space.
Low utilization: Most applications don’t use the server’s full capacity. Many servers stayed at 5–20% usage, wasting , memory, and storage resources.
Slow deployment: Setting up new physical servers could take days or weeks.
Hard to scale: If an application suddenly needed more resources, you often had to buy yet another server.

A virtualization layer, called a hypervisor, was introduced to act as a referee between lab machines and allow each virtual computer to behave independently, like a physical computer.

Each virtual computer, known as a Lab Machine (VM), acts as an independent system with its own operating system, apps, and settings, even though they all share the same physical hardware underneath.

