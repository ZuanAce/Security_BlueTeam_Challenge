# Challenge Scenario
In this activity you’ll be putting your new TCPDump skills to the test by analyzing two PCAPs. You will be able to complete both of the challenges using the knowledge we have covered in the previous lessons.
# PCAP 4
1. How many UDP packets have been captured?

   **Setup Using a Virtual Machine:**
   - Launch your VM (e.g., Kali Linux) to perform packet analysis.

   **Run tcpdump Command:**
   - Execute the command *tcpdump -r SBT-PCAP4.pcap udp --count* in the terminal to analyze the captured packets and count UDP packets specifically.
   - **3290 UDP packets were captured**
     
     ![image](https://github.com/ZuanAce/SecurityBlueTeam_challenge/assets/147037911/c538c704-36d9-427f-867e-0e206415fdda)

2. How many TCP packets have both the SYN and ACK flags set?

   **Calculate The Decimal Value of Flag:**
   - For packets with the SYN and ACK flags set, the decimal value becomes 0001010 = 18
     
     ![image](https://github.com/ZuanAce/SecurityBlueTeam_challenge/assets/147037911/c85cadb8-d9ae-4405-9a1c-687e87f368ad)
   
   **Run tcpdump Command:**
   - Execute the command *tcpdump -r SBT-PCAP4.pcap tcp[tcpflags] == 18 --count* in the terminal to analyze the captured packets and count TCP packets specifically.
   - **20 TCP packets**
     
     ![image](https://github.com/ZuanAce/SecurityBlueTeam_challenge/assets/147037911/ca910456-655f-4653-a954-62bb8e41a9b0)

3. Which version of Chrome was used to connect to securityblue.team?

   **Run tcpdump Command:**
   - Execute the command *tcpdump -r SBT-PCAP4.pcap -vvv | grep -i chrome* 
   - **Version 80.0.3987.87**
     
     ![image](https://github.com/ZuanAce/SecurityBlueTeam_challenge/assets/147037911/ae6f761e-821c-4e84-a655-8d7c767e65eb)


5. How many packets have a TTL value of 38?

   **Run tcpdump Command:**
   - Execute the command *tcpdump ip[8] == 38 -r SBT-PCAP4.pcap --count* 
   - **710 packets**
     
     ![image](https://github.com/ZuanAce/SecurityBlueTeam_challenge/assets/147037911/60f95be1-6af6-4a61-b187-a9d4b4b21b86)

# PCAP 5
1. What is the name of the PNG file on the webserver at 192.168.56.111?
   
   **Run tcpdump Command:**
   - Execute the command *tcpdump -A -r SBT-PCAP5.pcap | grep .png* to get the name of the PNG file on the web server at 192.168.56.111
   - **proprietary.png**
     
     ![image](https://github.com/ZuanAce/SecurityBlueTeam_challenge/assets/147037911/30f335c9-decd-4183-a87f-86d85ac26ac1)


2. Which version of OpenSSH is running on the server?

   **Run tcpdump Command:**
   - Execute the command *tcpdump -vvv -r SBT-PCAP5.pcap | grep OpenSSH* to check the version of OpenSSH
   - vvv for more verbosity output, greping OpenSSH
   - **OpenSSH-7.9p1**
     
     ![image](https://github.com/ZuanAce/SecurityBlueTeam_challenge/assets/147037911/791aa4e8-06d6-482d-8e3a-a2578a0ab037)

3. On which port is the .zip file being served?

   **Run tcpdump Command:**
   - Execute the command *tcpdump -A -r SBT-PCAP5.pcap | grep .zip -B 3* to find which port is the .zip file being served
   - **port 3016**
     
     ![image](https://github.com/ZuanAce/SecurityBlueTeam_challenge/assets/147037911/26c7ebc2-78c3-42e1-aa20-1dfc6c26c5d7)

5. When was a packet with a TCP checksum value of 53203 captured?

   This networking challenge that had me stumped until I switched from Tcpdump to Wireshark. 


   ![image](https://github.com/ZuanAce/SecurityBlueTeam_challenge/assets/147037911/70a102c8-ac12-4fdf-b25e-2d1993d01457)
   
   


    
  

# Thanks for Reading!!

