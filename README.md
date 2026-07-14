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

