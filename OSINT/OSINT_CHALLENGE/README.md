# Challenge Scenario and Details
You work for a law enforcement organisation, and you have been assigned to track a person-of-interest (POI), that is believed to be associated with a hacking group that recently compromised a Managed Service Provider (MSP) and are trying to sell the stolen credentials on both the clear net and dark web. Another team is focusing on the dark web lead, so you have been tasked with using OSINT sources to build up a profile on the individual and attempt to locate any evidence that links them to the MSP breach and sale of account details. You have been provided with some information to start your investigation. You should use any of the sources or tools taught in this course, that you deem to be applicable and appropriate. We know that the email address used to register the Twitter account is fake, so do not include this in your report.

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
I tried to use what I have learned to complete the OSINT challenge

Using the Google search query *allintext:sp1ritfyre* to find web pages where the term "sp1ritfyre" appears in the text content. 

![image](https://github.com/ZuanAce/Security_BlueTeam_Challenge/assets/147037911/ef3b5c22-e191-4524-8cf3-3c739fe6dcbc)

The first two searches look very promising. Clicking on the first one lead to the twitter handler and it can be seen that there was a link encoded with base 64.

![image](https://github.com/ZuanAce/Security_BlueTeam_Challenge/assets/147037911/c848b0c4-1860-44b2-a44b-2d25e2588582)

I decoded the link via [Cyberchef](https://gchq.github.io/CyberChef/) and obtained a link *redhunt.net*

![image](https://github.com/ZuanAce/Security_BlueTeam_Challenge/assets/147037911/330b743e-88a5-4843-805a-622b03a7d31c)

However, acessing the decoded link yielded no information regarding the POI. Thus, I proceeded with the second search which leads to the POI's blogpost.

![image](https://github.com/ZuanAce/Security_BlueTeam_Challenge/assets/147037911/a7294bac-cdc3-46af-9005-7889eaadd749)

There were two sections that caught my attention. 
- Contact me which may consists of POI's email address
  
  ![image](https://github.com/ZuanAce/Security_BlueTeam_Challenge/assets/147037911/e1d605fc-1d3f-469e-9113-d7f1ebd811dc)

- Location which was hexadecimal encoded

Decoded the string via [Cyberchef](https://gchq.github.io/CyberChef/) again and obtained https://sammiewoodsec.blogspot.com

![image](https://github.com/ZuanAce/Security_BlueTeam_Challenge/assets/147037911/bfd7b37d-1b92-4c73-a50d-537420e08f71)

Copy paste the link and finally, I founded the POI's blog and her profile.

![image](https://github.com/ZuanAce/Security_BlueTeam_Challenge/assets/147037911/15effdaf-68d0-40f7-9438-d0d3e4395905)

![image](https://github.com/ZuanAce/Security_BlueTeam_Challenge/assets/147037911/e9dcfa01-32cf-4c64-af2e-284809d42f72)

![image](https://github.com/ZuanAce/Security_BlueTeam_Challenge/assets/147037911/14bc9daa-46fe-4b29-a847-865606648c0e)

I can now confidently answer all the questions. 

**[1] First Name:** Sammie

**[2] Last Name:** Woods

**[3] Age:** 23

**[4] Country:** United Kingdom 

**[5] Interests (5 minimum):** Security, Gaming, Photography, Camping, Malware Analysis

**[6] Hacker's employer (company name):** PhilmanSecurityInc

**[7] Hacker's position within company:** Junior Penetration Tester

**[8] Self-Owned Website (Hacker owns the domain):** https://redhunt.net/
**[9] Other Websites (Person does not own the domain, such as blogs):** https://sp1ritfyrehackerstories.blogspot.com/ https://sammiewoodsec.blogspot.com/ https://github.com/SammieWoodSec

Evidence Collection:
=================================
**[10] Any URLs of webpages that directly tie individual to MSP breach:**

Email Addresses Utilised:
=================================
**[11] What email addresses have been used by the hacker?** d1ved33p@gmail.com











  
# Thanks for reading!!
