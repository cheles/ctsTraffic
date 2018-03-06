# ctsTraffic
Client to Server Traffic (ctsTraffic) was developed by members of the Microsoft (R) Windows (R) Networking test team. It was initially designed at the end of Windows 7 and has been used to measure networking scenarios throughout Windows 8 and Windows Blue. We are now excited to be bringing this tooling to the open source community.

It is a utility to generate and validate the integrity of network traffic. It is a highly scalable client / server application with the ability to send and receive traffic in a variety of protocol patterns, utilizing a variety of API calling patterns. The protocol is validated in bytes sent and received for every connection established. Should there be any API failure, any connection lost prematurely, or any protocol failure in bytes sent or received, the tool will capture and log that error information. 

ctsTraffic has been tested to scale down to small devices, scale up to large systems (effectively spanning across large #s of processors; large memory installations including multiple NUMA nodes; easily filling large network pipes including 10Gig and 40Gig connections), and scaling out to large numbers of simultaneous connections (tested up to 500,000 active TCP connections).

Information about the network traffic can be captured within an Excel-friendly format to facilitate graphing interesting properties of the network session; properties such as TCP bytes/second or UDP bits/second; UDP frames processed over time; UDP frames dropped over time; connection rates successfully established over time; failed connections over time.
Supported Features:
Servers service any number of connections from any number of clients
Allows for specifying the number of connections to maintain from the client
Allows targeting one or more servers by name or address
Allows binding or listening to specific addresses or ranges (e.g. only IPv6 addresses)
Allows for selecting the degree to which ctsTraffic should validate the TCP session (connection integrity or additionally data integrity)
TCP-specific
Allows for specifying the buffer sizes used in send & receive calls - including specifying a range to randomly select a buffer size
Allows for selecting from different Winsock API usage patterns
Allows for selecting from various TCP protocol patterns controlling send and receive patterns
Allows for throttling TCP connections to send at a specified rate
UDP-specific
Allows for controlling the bits/second being streamed from the server, processed on the client
Allows for controlling the frame to process the incoming stream
Allows for controlling the amount of buffering on the client before starting to process the stream
Allows for controlling how hard the client will work in looking ahead and requesting missing frames
Various logging options, including toggling whether to log to console
Text formatting or Csv formatting
Per connection details; error details; aggregate status details; UDP jitter details
Various logging options and verbosity, allowing greater levels of detail when required
Various scenario-specific options for customized environments
Setup Instructions:
Select the Downloads tab above. Copy ctsTraffic.exe to the client and server (no installation required - only a single binary).
Usage:
Server-side usage
 ctsTraffic -Listen:<addr or *> [-Port:####] [CommonOptions] 
