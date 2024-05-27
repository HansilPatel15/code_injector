<h1>code_injector</h1>


<h2>Description</h2>
- HTTP Traffic Injector Script <br>
<br>This script intercepts HTTP traffic and injects a custom JavaScript snippet into HTML responses. It captures and modifies packets using netfilterqueue and Scapy, removing "Accept-Encoding" headers and updating the content length after injection.<br>

<br>Features: <br>
- Packet Interception: Captures HTTP requests and responses using netfilterqueue and iptables.<br>
- Header Modification: Removes "Accept-Encoding" headers from requests to avoid compressed responses.<br>
- Content Injection: Injects custom JavaScript code into HTML responses and updates the Content-Length header.<br>
<br />


<h2>Languages and Utilities Used</h2>

- <b>Python</b> 


<h2>Environments Used </h2>

- <b>Linux</b> 

<h2>Usage: </h2>
 Run the script with the required options:
<br>sudo python http_injector.py
<br>Set up iptables rules:
<br>sudo iptables -I FORWARD -j NFQUEUE --queue-num 0
<br>sudo iptables -I INPUT -j NFQUEUE --queue-num 0
<br>sudo iptables -I OUTPUT -j NFQUEUE --queue-num 0

<br><b> Example: </b>
<br>
The script is configured to inject <script>alert('test');</script></body> into all HTML responses. Modify the injection_code variable in the process_packet function to customize the injected content.
<br>
<b>Requirements:</b><br>
- Python 3.x<br>
- Scapy library (pip install scapy)
- NetfilterQueue library (pip install NetfilterQueue)<br>
- Root or sudo privileges for packet manipulation<br>
