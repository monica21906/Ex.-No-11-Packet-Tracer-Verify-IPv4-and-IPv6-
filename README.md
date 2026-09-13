# Ex. No: 11 – Packet Tracer: Verify IPv4 and IPv6 Addressing
# Date: 9/9/2026
________________________________________<br>
# Objective
To configure, verify, and test dual-stack (IPv4 and IPv6) addressing on a Cisco Packet Tracer network topology.<br>
Tasks:<br>
• Document IPv4 and IPv6 addressing details.<br>
• Test connectivity using ping for both protocols.<br>
• Trace the route of packets to verify end-to-end connectivity.<br>
________________________________________<br>
# Apparatus / Tools Required
• Cisco Packet Tracer<br>
• 3 Routers (R1, R2, R3 – 2911 or equivalent)<br>
• 2 PCs (PC1, PC2)<br>
• Copper straight-through and Serial DCE/DTE cables<br>
________________________________________<br>
# Network Topology Diagram
(Insert your Packet Tracer screenshot showing R1–R2–R3 in series and PCs connected to edge routers.)<br>
________________________________________<br>
# Addressing Table
Device	Interface	IPv4 Address / Subnet Mask	IPv6 Address / Prefix	Default Gateway<br>
R1	G0/0	10.10.1.97 / 255.255.255.224	2001:db8:1:1::1/64	N/A<br>
R1	S0/0/1	10.10.1.6 / 255.255.255.252	2001:db8:1:2::2/64	N/A<br>
R2	S0/0/0	10.10.1.5 / 255.255.255.252	2001:db8:1:2::1/64	N/A<br>
R2	S0/0/1	10.10.1.9 / 255.255.255.252	2001:db8:1:3::1/64	N/A<br>
R3	G0/0	10.10.1.17 / 255.255.255.240	2001:db8:1:4::1/64	N/A<br>
R3	S0/0/1	10.10.1.10 / 255.255.255.252	2001:db8:1:3::2/64	N/A<br>
PC1	NIC	(IPv4 auto/DHCP)	(IPv6 auto-config)	R1 G0/0<br>
PC2	NIC	(IPv4 auto/DHCP)	(IPv6 auto-config)	R3 G0/0<br>
________________________________________
# Procedure
# Part 1: Verify IPv4 and IPv6 Addressing
1.	On PC1, open Command Prompt → enter:<br>
2.	ipconfig /all<br>
Record IPv4 address, subnet mask, and gateway.<br>
3.	On PC2, repeat the same.<br>
4.	For IPv6 verification:<br>
5.	ipv6config /all<br>
Record IPv6 address, prefix, and default gateway for both PCs.<br>
________________________________________<br>
# Part 2: Test Connectivity Using Ping
1.	From PC1, ping the IPv4 address of PC2.<br>
2.	ping 10.10.1.20<br>
o	Verify success (Reply from 10.10.1.20).<br>
3.	From PC2, ping the IPv6 address of PC1.<br>
4.	ping 2001:db8:1:1::a<br>
o	Verify success for IPv6 reachability.
________________________________________<br>
# Part 3: Discover the Path Using Traceroute
1.	From PC1, trace route to PC2 using IPv4:<br>
2.	tracert 10.10.1.20<br>
Observe the hops across R1 → R2 → R3.<br>
3.	From PC2, trace route to PC1 using IPv6:<br>
4.	tracert 2001:db8:1:4::a<br>
Record IPv6 path hops.<br>
________________________________________<br>
# Commands Used (Summary)
Purpose	Command<br>
Check IPv4 details	ipconfig /all<br>
Check IPv6 details	ipv6config /all<br>
Ping test (IPv4/IPv6)	ping <IP><br>
Trace path (IPv4/IPv6)	tracert <IP><br>
________________________________________<br>
# Verification & Testing
• Successful ping replies indicate proper dual-stack connectivity.<br>
• Trace route confirms correct path through routers R1–R2–R3.<br>
________________________________________
# Output (Attach Screenshots)
• ipconfig /all and ipv6config /all output for both PCs.<br>
<img width="1917" height="1021" alt="image" src="https://github.com/user-attachments/assets/5ee66933-5bd1-4373-866d-938ff88dd64a" />
<img width="1917" height="1017" alt="image" src="https://github.com/user-attachments/assets/714fb87c-b680-44f4-8100-630b19e4f9a3" />


• Ping results for IPv4 and IPv6.<br>
<img width="1566" height="575" alt="image" src="https://github.com/user-attachments/assets/3c5e8573-696b-405d-abe5-a66e56628cb4" />
<img width="1906" height="527" alt="image" src="https://github.com/user-attachments/assets/6f1ffb16-8cae-4ad6-9741-da3c13c77313" />


• Traceroute results showing intermediate hops.<br>
<img width="1917" height="1015" alt="image" src="https://github.com/user-attachments/assets/b807d02b-8931-433c-b791-3380048d8a99" />
<img width="1917" height="1020" alt="image" src="https://github.com/user-attachments/assets/acdadbba-1fac-4a67-9ace-7fcd575999c7" />

________________________________________
# Result
The dual-stack IPv4 and IPv6 addressing scheme was successfully verified. Both addressing types achieved full connectivity between PC1 and PC2 through multiple routers, confirming correct configuration and routing.

