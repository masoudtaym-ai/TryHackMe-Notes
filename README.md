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

##Intro

