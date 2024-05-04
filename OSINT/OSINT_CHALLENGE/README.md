# Challenge Scenario and Details
You work for a law enforcement organisation, and you have been assigned to track a person-of-interest, that is believed to be associated with a hacking group that recently compromised a Managed Service Provider (MSP) and are trying to sell the stolen credentials on both the clear net and dark web. Another team is focusing on the dark web lead, so you have been tasked with using OSINT sources to build up a profile on the individual and attempt to locate any evidence that links them to the MSP breach and sale of account details. You have been provided with some information to start your investigation. You should use any of the sources or tools taught in this course, that you deem to be applicable and appropriate. We know that the email address used to register the Twitter account is fake, so do not include this in your report.

Your manager has provided you with the following starting information:
- Twitter handle used by actor: @sp1ritfyre

```bash
 ___________   _____ _   ____   _______ ___   _      _     
|  _  | ___ \ /  ___| | / /\ \ / /  ___/ _ \ | |    | |    
| | | | |_/ / \ `--.| |/ /  \ V /| |_ / /_\ \| |    | |    
| | | |  __/   `--. \    \   \ / |  _||  _  || |    | |    
\ \_/ / |     /\__/ / |\  \  | | | |  | | | || |____| |____
 \___/\_|     \____/\_| \_/  \_/ \_|  \_| |_/\_____/\_____/
                                                           
                                                           
Investigation into MSP data breach. Clear web investigation team.

===============================++===============================


Known Info:
=================
Twitter Handle: @sp1ritfyre

Required Info:
=================
[1] First Name:
[2] Last Name:
[3] Age:
[4] Country:
[5] Interests (5 minimum):
[6] Hacker's employer (company name):
[7] Hacker's position within company:

Online Presence:
=================================
[8] Self-Owned Website (Hacker owns the domain):
[9] Other Websites (Person does not own the domain, such as blogs):

Evidence Collection:
=================================
[10] Any URLs of webpages that directly tie individual to MSP breach:

Email Addresses Utilised:
=================================
[11] What email addresses have been used by the hacker? (2)

===============================++===============================

```
# Approach
Do a simple google search on @sp1ritfyre gives us the following results:

![image](https://github.com/ZuanAce/SecurityBlueTeam_challenge/assets/147037911/9f5a54b9-c397-4751-a6f3-88d9214e7332)

For security, consider using a Virtual Machine (VM) or a VPN before connecting.

Open Tor Browser, connect, & paste the following link: [5xdv6dqxv2bsbmlgttsq3ma3nw6ffa2zhqbl7o4w46p32wsqulzrtsqd.onion](5xdv6dqxv2bsbmlgttsq3ma3nw6ffa2zhqbl7o4w46p32wsqulzrtsqd.onion)
![image](https://github.com/ZuanAce/SecurityBlueTeam_challenge/assets/147037911/3018f9ae-cc18-4ad8-847d-5094070af929)

Click on "GO TO THE CHALLENGE" to reach the login page:
![image](https://github.com/ZuanAce/SecurityBlueTeam_challenge/assets/147037911/e20b7966-65bd-4488-b871-a9168bc290a5)

Right-click, select "Inspect," navigate to the console, & execute the generateUserCredentials() command:
![image](https://github.com/ZuanAce/SecurityBlueTeam_challenge/assets/147037911/38c0ddd1-30f1-4f88-a577-b3f1a7a63ac1)

Get a Base64 encoded string & Lets Decode everything. I used [Cyberchef](https://gchq.github.io/CyberChef/) to decode 
![image](https://github.com/ZuanAce/SecurityBlueTeam_challenge/assets/147037911/91ee091b-737e-41ab-a163-181d586f5d0b)

Login using the decoded credentials. The content is all hexadecimal encoded!
![image](https://github.com/ZuanAce/SecurityBlueTeam_challenge/assets/147037911/27aba7da-ad86-493f-ad5b-3df1bac2ce59)
It's up tp you if you wanna decode everything 

Found the drug dealer's blog hehe (just recognise it via the image lol):

![image](https://github.com/ZuanAce/SecurityBlueTeam_challenge/assets/147037911/8975410a-b780-42e4-a72c-d4e3f90c372d)

Scroll down to find the suspect's username:

![image](https://github.com/ZuanAce/SecurityBlueTeam_challenge/assets/147037911/c5957841-386e-4ff6-842c-2c87caeeb4b7)

Utilize Google Lens or a similar tool for a reverse image search:
![image](https://github.com/ZuanAce/SecurityBlueTeam_challenge/assets/147037911/6f53e6a3-01b4-40d9-9545-fa9e79688072)

Identify posts indicating the suspect's US citizenship and vacation details:
![image](https://github.com/ZuanAce/SecurityBlueTeam_challenge/assets/147037911/c0532bd5-e974-45af-8d65-44c74566d622)
- Suspect Name: Kestener Richard
- Location: London, United Kingdom

Explore the last post for coordinates and date:
![image](https://github.com/ZuanAce/SecurityBlueTeam_challenge/assets/147037911/ee75c9fd-c348-46e4-b261-8774fc54b9d9)
- Coordinates: 51° 56' 57.2"N, 1° 19' 26.1"E
- Date: 31 Oct 20XX

This approach is sufficient enough to answer all the quiz questions presented in the challenge
# Tools Used:
- Google Lens
- Cyberchef
- Tor Browser
  
# Thanks for reading!!
