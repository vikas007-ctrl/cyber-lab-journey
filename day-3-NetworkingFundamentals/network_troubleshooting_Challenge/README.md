# Commands used
hostname > step1_hostname.txt
ip addr > step2_ip.txt
ping -c 4 8.8.8.8 > step3_ping_ip.txt
ping -c 4 google.com > step4_ping_dns.txt
traceroute google.com > step5_traceroute.txt
curl -I https://www.google.com > step6_curl.txt
netstat -tuln > step7_netstat.txt

# What insights Each commands give about connectivity 

# Step 1 – Check Hostname

Command:  

hostname

-If output looks fine (e.g., kali), system is identified.

-If it fails, maybe hostname misconfigured.

# Step 2 – Check IP

Command:

ip addr

-Look for inet 192.168.x.x.

-If no IP assigned → problem with WiFi/LAN connection.

# Step 3 – Ping a Public IP

Command:

ping -c 4 8.8.8.8

Outcomes:

-Works = Internet connection is fine.

-Fails = ISP / router issue.

# Step 4 – Ping a Website

Command:

ping -c 4 google.com

 Outcomes:

-Works = DNS + Internet both fine.

-Fails but Step 3 worked = DNS issue.

# Step 5 – Traceroute

Command:

traceroute google.com

-Shows where the connection breaks.

-If Stops at 192.168.1.1 → local router issue.

-if Stops at ISP backbone → ISP issue.

#  Step 6 – Curl Test

Command:

curl -I https://www.google.com

-If you see 200 OK → Website is alive.
-If you see 301 → Redirect, but still alive.
-If no response → Firewall or DNS problem.

# Step 7 – Check Your Own Machine’s Ports

Command:

netstat -tuln

-Confirms which services are running locally.
-Example: SSH open at port 22, web server at port 80. 
-checks port conflicts,tcp/udp listerners are functional locally 

