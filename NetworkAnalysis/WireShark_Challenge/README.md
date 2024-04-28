# Challenge Scenario
In this activity, you’ll be putting your new Wireshark skills to the test by analyzing two PCAPs, which increase in difficulty. You will be able to complete both challenges using the knowledge we have covered in the previous course lessons.
# PCAP 1
1. Which protocol was used over port 3942?

   **Protocol Investigation:**
   - Open Wireshark and navigate to Statistics > Endpoints > UDP.
   - Right-click on the line with port 3942 and select "Apply as Filter" > "Selected."
   ![image](https://github.com/ZuanAce/SecurityBlueTeam_challenge/assets/147037911/33262e68-723a-48fc-bfa6-e85afe537d13)

   **Check Protocol:**
   - Return to the main screen of Wireshark to view the filtered traffic.
   - The protocol used over port 3942 is identified as **SSDP**
   ![image](https://github.com/ZuanAce/SecurityBlueTeam_challenge/assets/147037911/b41ccebe-9f8e-481e-a756-cfe4618e73a4)

2. What is the IP address of the host that was pinged twice?

   Ping works by sending ICMP Echo Requests to a specified network interface and awaiting a response.
   
   **Display Filter Setup:**
   - Type icmp in the display filter bar to focus on ICMP traffic.
     
   **Identifying Ping Requests:**
   - The analysis reveals two ICMP Echo Requests sent to the IP address **8.8.4.4**.
   ![image](https://github.com/ZuanAce/SecurityBlueTeam_challenge/assets/147037911/23a95d27-79da-419b-9c45-411fea2bc122)

3. How many DNS query response packets were captured?

   **Apply DNS Display Filter:**
   - Type **dns** in the display filter bar to focus on DNS-related packets.
   ![image](https://github.com/ZuanAce/SecurityBlueTeam_challenge/assets/147037911/77f04bb8-ad85-416e-9b70-9ae15e7a7201)

   **Select Standard Query Response:**
   - Select the first packet labeled "standard query response" in the packet list.
   
   **Filter Response Packets:**
   - In the frame display section, navigate to Domain Name System > Flags.
   - - Right-click on the entry labeled "response: message is a response" and choose "Apply as Filter" > "Selected."
   ![image](https://github.com/ZuanAce/SecurityBlueTeam_challenge/assets/147037911/d12e6af1-6c00-45ee-98b0-9fd840e51a22)

   **Check Packet Count:**
   - Check the displayed packets in the lower right-hand side of Wireshark.
   - The number of DNS query response packets captured is **90**.
   ![image](https://github.com/ZuanAce/SecurityBlueTeam_challenge/assets/147037911/dd2179eb-3c38-418c-8fed-b8b3d19f7383)

5. What is the IP address of the host which sent the most number of bytes?

   **Navigate to Statistics:**
   - Go to Statistics > Endpoints > IPv4 in Wireshark.
   
   **Sort by Tx Bytes:**
   - Click on Tx Bytes (transmit bytes) to display the results in descending order
   - Rx Packets are received by a device, while Tx Packets are transmitted by a device.
   - Based on transmit bytes statistics, the identified IPv4 address is 115.178.9.18.
   ![image](https://github.com/ZuanAce/SecurityBlueTeam_challenge/assets/147037911/38b781df-3e5d-4955-9a5d-0e50cabe1cfb)


# PCAP 2
1. What is the WebAdmin password?
   
   **Filter HTTP Traffic:**
   - Since it is related to web, I decided to check HTTP traffic. Typed in **http** in display filter.
     ![image](https://github.com/ZuanAce/SecurityBlueTeam_challenge/assets/147037911/889a3cc0-dde6-468a-83e0-85172ac5b596)
   
   **Identify Suspicious Packet:**
   - Packet 4121 stands out due to a GET request for a file named password.txt.
     ![image](https://github.com/ZuanAce/SecurityBlueTeam_challenge/assets/147037911/80d182bc-5855-4e1b-ab57-2044d0addaae)

   **Follow HTTP Stream:**
   - Right-click on packet 4121 and select "Follow" > "HTTP Stream."
   - Discover the password **sbt123**
     
     ![image](https://github.com/ZuanAce/SecurityBlueTeam_challenge/assets/147037911/ec652ef0-098f-4add-aada-ac6ab535b752)

2. What is the version number of the attacker’s FTP server?

   **Filter FTP Traffic:**
   - Based on the previous question, we can infer that the device used to get the password.txt file is the attacker.
   - Type "ftp and ip.src == 192.168.56.1" in the display filter to focus on FTP traffic originating from the attacker's IP address.
     ![image](https://github.com/ZuanAce/SecurityBlueTeam_challenge/assets/147037911/82285e2d-baca-4982-94ca-58b3ee02bc72)
   
   **Inspect Packet Details:**
   - Check the frame display section of packet 4243 for details regarding the FTP communication.
   - A brief Google search on pyftpdlib, which is a Python FTP server library, reveals that the version used is 1.5.5.
    ![image](https://github.com/ZuanAce/SecurityBlueTeam_challenge/assets/147037911/5f8cafd6-dd88-476e-afca-5b0fdcd1d3e4)

3. Which port was used to gain access to the victim Windows host?

   **Filter Traffic from Compromised Host:**
   - Type ip.src == 192.168.56.1 in the display filter to focus on traffic originating from the compromised host.
   
   **Review HTTP Traffic:**
   - Identify HTTP traffic where the attacker downloaded the password.txt file.
   - Examine packet 4128, which follows the HTTP traffic.
     ![image](https://github.com/ZuanAce/SecurityBlueTeam_challenge/assets/147037911/b73c4d0b-3b7e-4d44-81a7-ce42565848cf)
     ![image](https://github.com/ZuanAce/SecurityBlueTeam_challenge/assets/147037911/916d8b4e-3214-4806-bb59-cbd0e22294df)
   
   **Follow TCP Stream:**
   - Right-click on packet 4128 and select "Follow" > "TCP Stream."
     ![image](https://github.com/ZuanAce/SecurityBlueTeam_challenge/assets/147037911/3e30d3d7-4947-4519-b88f-7605a6053442)
     ![image](https://github.com/ZuanAce/SecurityBlueTeam_challenge/assets/147037911/84d87fc7-2947-4e1d-a843-eb228cb37647)
   - Analyze the TCP stream to see the attacker moving to the desktop, listing files, and creating a text file with FTP commands.
   
   **Find Destination Port:**
   - Return to the main screen and locate the destination port used by the attacker.
   - The port is **8081**
     ![image](https://github.com/ZuanAce/SecurityBlueTeam_challenge/assets/147037911/d9b9fe76-191b-48f1-b264-04d180f5499f)

4. What is the name of a confidential file on the Windows host?

   **Follow TCP Stream:**
   - Right-click on packet 4128 and select "Follow" > "TCP Stream" in Wireshark.
   
   **Review Files in Desktop Directory:**
   - Examine the TCP stream to explore the actions taken by the attacker.
   - Discover the presence of a file named "Employee_Information_CONFIDENTIAL.txt" in the Desktop directory.
     ![image](https://github.com/ZuanAce/SecurityBlueTeam_challenge/assets/147037911/7ad7e828-4bf6-4848-9590-3b4ef37ff515)

6. What is the name of the log file that was created at 4:51 AM on the Windows host?
   **Follow TCP Stream:**
   - Right-click on packet 4128 and select "Follow" > "TCP Stream" in Wireshark.
   
   **Review Files in Desktop Directory:**
   - Examine the TCP stream to explore the actions taken by the attacker.
   - Discover the presence of a file named "LogFile.log" in the Desktop directory at 4:51am.
     ![image](https://github.com/ZuanAce/SecurityBlueTeam_challenge/assets/147037911/32dd895d-eeb0-4833-9cec-564620e95544)

# Thanks for Reading!!
