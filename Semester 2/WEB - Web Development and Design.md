<label>Lecture 01 - 2022/10/04</label>
# Introduction
Outline,
	1. Internet, its history and its functionality
	2. Protocols
	3. IP addresses

# Internet
Internet? It is a worldwide network of computer networks.
	- Follow standard communication rulesets. *Ex: RSS, HTTP, HTTPS, WSS, SMTP*
	- It is designed to interconnect all types of networks.
	- No one controls or owns the internet, but to connect to is you need a machine that obeys the protocols.

Internet vs WWW?
	- Internet is a network and www is a service inside it. There are many other services running on top of the internet, like Mail services etc.
	- The internet is just a wide spread network of devices, services that run on top of it may vary in nature.

## How the internet works
It is based on a client server model. In this model,
	- Each computer is given a unique address to be identified with.
	- Both the client and server computers follow the same protocol to communicate data.

Two technologies commonly followed in the client server model,
	- Pull technology,
		Client initially requests the desired data and the server provides it.
	- Push technology,
		Client initially requests the desired data and the server establish some sort of autonomous data retrieval method so that the server can push data to the client freely.
			- This is normally done by running some sort of service worker on the client device.
			- It is widely used to keep real time communications up and running.

## Internet Protocols
What is a protocol? A set of rules that govern the data communication over a network.

What is the internet protocol suite? A set of communication protocols used in the internet and similar computer networks.
	1. TCP  : Provides reliable transmission with slower speeds.
		- Checks for errors
		- Acts as a transport layer
		- It is connection oriented
		- Used at reliability is needed over speed.
	2. UDP  : Faster transmissions but it is not reliable.
		- It is not connection oriented
		- Used for VOIP (Voice over IP), Streaming and cases where speed matters over security.
	3. IP   : 
	4. HTTP : 
	5. SMTP : 
	6. WAP  : 
	7. POP3 : 

## Evolution of the internet
Internet was based on the idea that there would be multiple independent networks of rather arbitrary design, beginning with the ARPANET as the pioneering packet switching network, but soon to include packet satellite networks, ground-based packet radio networks and other networks.
	- Department of defense developed USA ARPANET.
	- Late 1980s' US National Science foundation started exploring ways to enable access of their supercomputer to researchers.
	- [Tim Berners Lee](https://en.wikipedia.org/wiki/Tim_Berners-Lee) created the WWW in 1990
	- At first WWW was a house of documents to store information

***