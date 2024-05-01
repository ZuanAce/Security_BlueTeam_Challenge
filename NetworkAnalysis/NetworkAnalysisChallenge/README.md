# Challenge Scenario
Alexis is a fictional cybersecurity company with thousands of employees. An attacker has gained unauthorized entry into its premises and has connected their laptop to an unused port on a switch. The attacker now has access to the company’s internal networks. Within the internal network, there is a central server where critical proprietary data is stored. In this capture, the attacker is attempting to collect SSH credentials that they can use to log into the central server.
# PCAP 3
1. What is the MAC address of the attacker?

   **Filtered SSH Packets:**
   - Applied *ssh*  filter in Wireshark to narrow down packets to 142 for inspection.
     ![image](https://github.com/ZuanAce/SecurityBlueTeam_challenge/assets/147037911/2a0cbc11-be19-4ff5-96f9-79517f80a034)
   
   **Conversations Analysis:**
   - Examined Statistics > Conversations, revealing only two devices communicating via SSH.
     ![image](https://github.com/ZuanAce/SecurityBlueTeam_challenge/assets/147037911/3fb02e1d-2567-4014-9eb3-d06dd9efa409)
   
   **Packet Inspection:**
   - Reviewed packet 765 on the main screen, focusing on Ethernet details.
   - Attacker's MAC Address: 08:00:27:3d:27:5d
     ![image](https://github.com/ZuanAce/SecurityBlueTeam_challenge/assets/147037911/f436695b-2c3e-45ac-91d9-b95ac2139018)

2. What is the type of attack which is taking place that allows the attacker to listen in on conversations between the central server and another host?

   - Just a simple google search will find the answer
   - Man-in-the-Middle
     
3. What is the file which was downloaded from the central server?

   **Protocol Overview:*8
   - Navigated to Statistics > Protocol Hierarchy in Wireshark to analyze all protocols in the PCAP file.
   - Identified FTP traffic under the TCP protocol.
   - FTP stands for File Transfer Protocol. It's a standard network protocol used for transferring files between a client and a server on a computer network.
     ![image](https://github.com/ZuanAce/SecurityBlueTeam_challenge/assets/147037911/bf9f1f5c-20eb-48de-90a4-38f7418eeaa5)
   
   **FTP Packet Inspection:**
   - Returned to the main screen and applied an FTP filter using ftp in the display filter.
   - Selected packet 550 and followed the TCP stream.
   - File Name: Alevis_Employee_Information_Chart.csv
     ![image](https://github.com/ZuanAce/SecurityBlueTeam_challenge/assets/147037911/c98c92e4-22e4-4454-a140-9383dafd4442)

4. What department does Borden Danilevich work in?

   **Filter FTP Traffic:**
   - Applied the FTP filter by typing ftp in the display filter box in Wireshark.
   - Followed the TCP stream and selected Stream 1 from the lower-right corner of the open window.
   - Revealed the contents of the CSV file within the TCP stream.
     ![image](https://github.com/ZuanAce/SecurityBlueTeam_challenge/assets/147037911/6d8cb22d-32db-4585-8674-3d2d1f15583d)
     ![image](https://github.com/ZuanAce/SecurityBlueTeam_challenge/assets/147037911/77d0a92a-2dd9-4ec9-8b9c-ba613d51ca3a)
   
   **Department Search:**
   - Conducted a search within the CSV file for the keyword "Borden" to identify his department information.
   - Sales
     ![image](https://github.com/ZuanAce/SecurityBlueTeam_challenge/assets/147037911/56cd6cf7-422c-486b-a134-0415ccfec64f)

6. What is the SSH password of the Domain Administrator?

   **Admin Search:**
   - Conducted a search within the CSV file for the keyword "Admin" to identify the SSH password.
   - Password is gMR<4eXf]e6W
     ![image](https://github.com/ZuanAce/SecurityBlueTeam_challenge/assets/147037911/3238dca4-f89f-4abd-acb6-7f67d85e4315)

# Thanks for Reading!!
Completing the Network Analysis course was a significant achievement for me. I faced challenges, particularly because I lacked sufficient networking knowledge. However, the learning experience was incredibly valuable, and I gained a wealth of knowledge. I would enthusiastically recommend this course to beginners who are looking to learn more about networking.
