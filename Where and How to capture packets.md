# Before Capturing:

Impact: Consider who/what is affected (individuals, groups, specific areas) and if the capture is continuous, ongoing, or temporary.
Applications: Identify the applications involved (email, database, etc.).
Servers: Determine if servers are local or cloud-based.
Network Path: Trace the network path the traffic traverses.
Capture Methods (Switched Environments):

# Wireshark on Endpoint (Pros & Cons):

Pros: Quick and easy setup.
Cons: Increases workload on the machine/server.
SPAN/Mirror:

Description: Instructs a switch/router/firewall to forward packets to a monitoring port.
Pros: Capture traffic from the internal network.
Cons: Avoid overloading the monitoring port by limiting the number of forwarded ports.

# TAP:

Description: A hardware device inserted between client and server to capture traffic.
Capturing at Multiple Locations:

Reason: Packet captures from different points (client vs. server) can reveal variations in network traffic.
Identifying Retransmissions:

Recommendation: Capture from both client and server sides for better troubleshooting.

# Capture Filters:

Use Cases: When you know exactly what traffic to capture (e.g., TCP traffic).
Caution: Filters can exclude relevant conversations.
Recommendation: Capture everything and filter later for better analysis.
Wireshark Capture Interface:

Start/Stop: Blue fin (start), red box (stop).
Capture Options:
Promiscuous mode: Capture all traffic (not just for your device).
Snaplen: Controls the amount of data captured per packet (default captures entire frame).
Buffer: Defines the capture data rate.
Interface Management: Limit the interfaces Wireshark sees.
Capturing Intermittent Problems:

Solution: Long-term capture configuration to record even unexpected issues.
Long-Term Capture Configuration:

Go to Capture Options.
Choose an interface.
Go to Output.
Start Capture.
Ring Buffer:

Function: Splits the capture into manageable files of a specific size.
Benefits: Easier to track and analyze captures with timestamps (helps identify incidents).
Saving Captured Traffic:

File Naming: Assign a descriptive name and save location.
Output Format: pcapng (recommended for capturing metadata).
File Segmentation: Choose automatic file creation options (by size or number).
Command-Line Capture (dumpcap):

