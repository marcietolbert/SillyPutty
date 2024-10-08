# Logical Diagram

## Introduction
In the MYDFIR SOC Analyst Challenge, day one required me to create a logical diagram for the project. I was eager to tackle this task as I understood the importance of being able to create logical diagrams for real production enviroments. In the passages that follow, I will explain the technical aspects of creating both a static and animated diagram. First, however, let's delve into some theory.

## What is a Logical Diagram
So, just what is a logical diagram? First, I'll start by defining what a network diagram is. A network diagram is a visual representation of a computer or telecommunications network that uses icons and lines to depict the devices within an environment and how they are connected. Network diagrams can fall into two categories: physical and logical. 

A physical diagram illustrates the physical components and connections within a network through the use of icons (physical components) and lines (cable connections). In contrast, a logical diagram shows how devices communicate with each other. However, instead of the lines representing physical cabling, the lines represent data flow. 

Here are some of the most common types of symbols that can be found in a logical diagram.

![image7-3](https://github.com/user-attachments/assets/08c5f8f3-1465-43b6-8e27-b4a576a825e7)
*Photo: via <a href="https://miro.com/blog/network-diagram/">Miro</a>*
<br>
<br>
![image1-10](https://github.com/user-attachments/assets/f4885289-be80-4347-a1c4-8406e79b23bd)
*Photo: via <a href="https://miro.com/blog/network-diagram/">Miro</a>*

## Logical Diagram Requirements
To begin constructing the logical diagram for this project I need to know what devices and environments to include in the diagram. The day-one video mentioned that my diagram should include the Internet, a Vultr cloud, a VPC (virtual private cloud), six servers, an Internet Gateway, and two computers. I'll be using Draw.io to create my logical diagram.

The devices to be depicted in the diagram are as follows:
- Elastic & Kibana Server
- Windows Server (RDP enabled)
- Ubuntu Server (SSH enabled)
- Fleet Server
- osTicket Server
- C2 Server (Mythic)
- Internet Gateway (Internet Service Provider)
- Computer (SOC Analyst laptop)
- Computer (Attacker laptop, Kali Linux OS)

The diagram should also include the following information about the VPC network:
- Private Network: 172.31.0.0/24
- IP Range: 172.31.0.1-254
- Subnet Mask: 255.255.255.0

## Device Connections and Data Flow
This section will cover where the devices for this project are placed in the enviroment and how data flows between them. Let's start by taking a look at the completed static and animated logical diagrams I created for this project.
<br>
<br>
<br> 

![Logical_Diagram drawio(1)](https://github.com/user-attachments/assets/1dda831b-32b2-4deb-9abc-e0191839beb5)

*Image 1: Static Logical Diagram*
<br>
<br>
<br>
![Logical_Diagram_Animated](https://github.com/user-attachments/assets/1218176a-9e64-4d2c-a8c4-c4ccdf07e005)

*Image 2: Animated Logical Diagram*
<br>

The breakdown of the devices and connections are as follows:
- Vultr - cloud provider for Windows and Ubuntu Servers (these servers have initially been placed into the VPC for the diagram but will be pulled out into the Vultr environment in an updated diagram)
- VPC - contains the Elastic/Kibana, osTicket, and Fleet Servers
- The Windows and Ubuntu Servers are connected to the Fleet Server with managed connections
- The Fleet Server is connected to the Elastic/Kibana Server with a bidirectional connection that indicates there are managed agents
- The osTicket Server is connected to the Elastic/Kibana Server with a bidirectional connection that indicates alerts/tickets information is being passed between the two
- The Windows and Ubuntu Servers need to be connected to the Elastic/Kibana Server with a connection that indicates that logs are being forwarded via agent from each server to the Elastic/Kibana Server
- The Internet is connected to the Internet Gateway
- The Internet Gateway is connected to VPC
- The SOC Analyst Laptop is connected to the Internet with a connection that indicates it can connect to the Elastic/Kibana Server via a web GUI
- The Attacker Laptop and the C2 Server are connected to the Internet

For a cleaner presentation:
- All of the connections should be changed to straight lines
- All connections to the Elastic/Kibana Server and the osTicket Server should be dashed
- If the icons chosen to be used can be colored they chould be to differentiate the devices from one another
- The connections from the Elastic/Kibana Server to the Fleet and osTicket Servers should be set to two different colors

Please note that the diagrams above are not final and will be updated as the enviroment is establised. This, however, is a great start to visualizing what the intented enviroment will look like and how it will function.
