# 1. Analyzing HTTP Response Time (http.time)
Wireshark provides a built-in metric called http.time. This value represents the time it takes for a web server to respond after receiving a request.
A general rule of thumb suggests investigating responses exceeding 2 seconds.
Finding Slow Responses:

Capture network traffic while reproducing the slow application behavior.
In Wireshark, locate the HTTP request-response sequence for the application.
Look for the http.time value displayed in the bottom left corner of the packet details pane.
If http.time is greater than 2 seconds, further investigation is needed.
Important Note: High http.time values don't automatically indicate server-side issues. Client-side delays (e.g., user input) can also contribute.

# 2. Measuring Secure Application Response Time (Delta Time)
Secure connections (HTTPS) encrypt data, making it difficult to directly measure response time using http.time.
Wireshark allows calculating response time for HTTPS by analyzing the delta time between the request and the corresponding response.
Finding Slow HTTPS Responses:

Capture network traffic with the slow application.
Identify the HTTPS request-response sequence for the application.
Calculate the delta time by subtracting the timestamp of the request from the timestamp of the response.
Investigate responses with significant delta times.

# 3. Differentiating Between Client and Server Slowness
High delays after sending a request might not always indicate server issues.
Clients can contribute to slow response times due to user interaction (e.g., entering passwords).
Distinguishing Client vs. Server Delays:

Look for large gaps between sending a request and receiving a response.
Consider if the delay aligns with a user interaction point within the application.
Correlate slow response observations with user complaints about specific actions.
If slow responses occur consistently without user interaction, investigate server-side issues.

# 4. Identifying High Network Latency
Network latency refers to the round-trip time it takes for a data packet to travel from the client to the server and back.
Frequent high latency (e.g., 40ms or more) can contribute to a sluggish user experience.
Detecting High Latency:

Examine the round-trip time (RTT) displayed during the TCP handshake within Wireshark.
Analyze the frequency of high RTT values. Consistent high latency suggests network issues.
Additional Tips:

High latency can be caused by congested networks or geographical distance between client and server.
# 5. Investigating Network Packet Loss
Packet loss occurs when data packets fail to reach their destination.
Packet loss can significantly impact application performance, causing delays and errors.
Identifying Packet Loss:

Look for retransmissions within the TCP stream in Wireshark. Retransmissions indicate packet loss.
Investigate Frame Check Sequence (FCS) errors, which might signify faulty network hardware (cables, transceivers).
Additional Points:

Packet loss can also be caused by network congestion.
