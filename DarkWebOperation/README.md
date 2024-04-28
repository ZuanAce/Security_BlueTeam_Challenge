# Challenge Scenario and Details
```bash
Hi Investigator, we need you...

Last month we were informed about a huge drug trafficking network that was taking place in the UK through the TOR network, in response to this situation we set to work and managed to dismantle their main TOR marketplace to stop drugs reaching the streets of the UK. However, we were informed that one of the creators of this network managed to evade us and is now continuing to carry out this type of activity. This is where you come in. We think we have found the site that this individual uses to "tell their stories" regarding criminal activity.

We need you to find evidence that will allow us to identify this subject, relate it to the drug trafficking crimes, and bring them to justice. We know this is a difficult task, but we are confident in your abilities and we are sure that you will succeed.

1] Gain access to the site (We're sure there's some way for users to gain valid credentials fairly easily).
2] Find evidence that the individual is involved in drug trafficking.
3] Find any information about the next shipment that is coming in, so we can seize it.
-------------++---------------++---------------++---------------++--------------

                    _********************_
=================== \  CHALLENGE REPORT  / ====================
                      ******************
  _________________________________________________   
 |   ___                                           | 
 |  |    \          __      ___  _____  _____      | 
 |  | |\  \        / /     Â´ _ `Â´  __ `Â´  ___`     | 
 |  | | \  \  /\  / /     | | | | !_/ /! Â´--.      | 
 |  | | /  /\/  \/ / ___  | | | |  __/  `--. Â¡     |
 |  | !/  /\  /\  / Â´   ` ! !_! ! |    /`--Â´ !     |
 |  !____/  \/  \/  `---Â´  `___Â´!_!    `----Â´      |
 |                                           (SBT).|
  ------------------------------------------------- 

 Known Info:
===================				      
[*] DWebsite:  5xdv6dqxv2bsbmlgttsq3ma3nw6ffa2zhqbl7o4w46p32wsqulzrtsqd.onion

 Requested Info:
==============================
1) What command is used in the Console to generate valid credentials?
2) What is the suspect's site username?
3) What is the suspect's first and last name?
4) What country is the suspect currently living in?
5) What is the date of the first post related to drug trafficking?
6) What is the date of the latest post related to drug trafficking?
7) What type of encoding has been used on the site content?
8) When is the next drug shipment coming into the UK?
9) What are the GPS coordinates of the shipment delivery location?  
10) What is the name of the seaport where the shipment is being delivered?
```
# Approach
Download Tor Browser from [here](https://www.torproject.org/download/)

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





