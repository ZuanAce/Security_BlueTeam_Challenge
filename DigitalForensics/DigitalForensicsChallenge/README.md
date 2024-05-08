# Challenge Scenario and Details
The SOC has received an anonymous report that a user is potentially exfiltrating data from the company. An image of the user’s hard drive has been taken, and you are responsible for analyzing the contents of a perfect copy to find any evidence of malicious activity. Using your newly developed skills, search through the folders and files using techniques to uncover 4 pieces of hidden information (each piece of evidence will contain the string {1 of 4} or similar). You will be tested on your ability to discover this information using all of the techniques taught in this course; Linux CLI navigation, identifying incorrect file extensions, identifying hidden files/folders, steganography, and password cracking.

# What will I need for this Challenge?
- Virtualbox (https://www.virtualbox.org/wiki/Downloads) or any alternative Virtual Machine software (VMWare etc)
- Kali Linux VM (https://www.kali.org/downloads)
- Challenge Disk Image (.zip file for ease-of-use. Download this to your Kali VM, unzip, and get going! Bottom of page)

# Starting Point
You have been told that the most recent file on the hard-drive was an email file with an attachment in the “Saved Emails” directory. It is suggested you start there. Below are some tips for your investigation:

- Always keep an eye out for hidden files that start with a ‘.’ – use ‘ls -a’ in a terminal to view these files!
- Look at the directories and files both in the Kali Linux GUI, and Command-Line!
- This challenge is based on a narrative. You will be gently guided to find some pieces of evidence, but remember to look in all folders, and check all files, especially ones that look strange!
- If you need to bypass a password-protected .zip use fcrackzip with the rockyou.txt word list.
- If you get stuck, ask people in the forensics module chatroom on our Discord server! Work together, learn together.

# Approach 
# Evidence 1
1. Launch kali linux and then download the file.
2. Unzip the file using the command *unzip filename* replacing the filename with the name of the downloaded file
3. Navigate to *J Harrison Disk Image 10.09.2019* using the command *cd 'J Harrison Disk Image 10.09.2019'*

   ![image](https://github.com/ZuanAce/Security_BlueTeam_Challenge/assets/147037911/7c3ece5d-84c0-4d36-98ae-5906c0b5dee2)


5. Using the *tree* command to display the directory structure in a tree-like format. It shows the hierarchy of directories and their subdirectories along with files. The tree command is particularly useful for visualizing the organization of files and folders within a directory. This will give me a better insight into where to look. Disclaimer: If you don’t have this command, you can install it using *sudo apt-get install tree*

   ![image](https://github.com/ZuanAce/Security_BlueTeam_Challenge/assets/147037911/f3c64d44-5908-4b1f-bb7f-cf6a46b50c5b)
   
   ![image](https://github.com/ZuanAce/Security_BlueTeam_Challenge/assets/147037911/4f42749c-32da-45a6-b079-4569479e24d6)


6. After spending a considerable amount of time exploring the "Disk Drive," I came across an empty directory named "to-do." Although it appears empty at first glance, if you use the command *ls -a*, you'll discover that it actually contains a hidden zip file. I attempted to extract its contents, but unfortunately, it seems to be encrypted with a password.

   ![image](https://github.com/ZuanAce/Security_BlueTeam_Challenge/assets/147037911/61f04159-439d-4032-84f7-d003ff295fe1)

7. Unable to locate any obvious passwords within the Disk Drive, I resorted to using *fcrackzip*. Using the command *fcrackzip -D -p /usr/share/wordlists/rockyou.txt -u .a0415ns.zip* to conduct a dictionary attack against the zip file. The password: *vendy13031988* was found. 

   ![image](https://github.com/ZuanAce/Security_BlueTeam_Challenge/assets/147037911/cb380b01-84ad-48f9-8f2f-aa0c8768e960)

8. Upon successfully unlocking the zip file, I came across a text document titled *employeedump*. The contents of this file appear to include confidential personal information about employees, which should not have been stored on this user's device.

   ![image](https://github.com/ZuanAce/Security_BlueTeam_Challenge/assets/147037911/00cb235b-17f8-456e-babc-dcc338a5f0b4)

# Evidence 2
1. I began examining the *Images* directory to see if there is any potential valuable information, given that stegofiles are often encountered in training scenarios. To verify the file extensions, I executed the *file** command, and then I used *ls -l* to check the file sizes. I observed that the *laptop.jpg* and *office 2.jpg* files had an unusually large byte size for a typical image, making them sus.

   ![image](https://github.com/ZuanAce/Security_BlueTeam_Challenge/assets/147037911/abdc6fae-41c1-4a53-87c5-338cb8b156be)

2. Tried using *steghide* commands on both the files. Turned out that the both files are stegofiles! So now we just have to look for the passwords!

   ![image](https://github.com/ZuanAce/Security_BlueTeam_Challenge/assets/147037911/5df44130-59c9-4d6f-a5d4-6001e57d15cd)

3. I checked out the *Saved Email* directory to see if there was anything noteworthy. The image I found didn't seem important, and steghide couldn't uncover anything either. So, I decided to use the *strings Form1.jpg* command to dig deeper for any valuable ASCII text, and what I found was pretty shocking. **Simon, I have usernames and passwords for the VPN. Still on my work PC. Don't want to risk emailing them just yet. When I do, the file is a .jpg image + password for extraction is password. Use steghide. Talk again soon**. This message shows that the .jpg stegfiles all have a password of *password*. 

   ![image](https://github.com/ZuanAce/Security_BlueTeam_Challenge/assets/147037911/9f4218b8-9a51-4d5b-8656-2bdb2cb214df)

   ![image](https://github.com/ZuanAce/Security_BlueTeam_Challenge/assets/147037911/93565f59-5721-4023-a3b8-dd25004bf7dd)

4. Navigating back to *Images* directory, then use the password: *password* and the command *setghide extract -sf laptop.jpg* to extract the embeded file. A file *passwords* is obtained. Using the *cat passwords* command, a list of employees' passwords were displayed.
   
   ![image](https://github.com/ZuanAce/Security_BlueTeam_Challenge/assets/147037911/c17c010f-911e-47d7-9f33-f1f2df97b107)

# Evidence 3
1. I ran the command *steghide extract -sf filename* on other suspicious .jpg files. However, there was nothing.

   ![image](https://github.com/ZuanAce/Security_BlueTeam_Challenge/assets/147037911/99a2bd61-af9d-42d2-aaaa-a6c43740d4fd)

   ![image](https://github.com/ZuanAce/Security_BlueTeam_Challenge/assets/147037911/9d5693fa-b740-4be2-ada4-0ab1d8c64369)

2. As I navigated through the directories, I came across an interesting file in the Week 10 directory. At first glance, it appeared to be an .xml file, but when I ran *file** command, it turned out the extension of the file is wrong. It is a PNG file!

   ![image](https://github.com/ZuanAce/Security_BlueTeam_Challenge/assets/147037911/4602ba23-cade-4503-a321-c2bd21c328ca)

3. Using the command *mv posidon.xml posidon.png* to change the extension from *.xml* to *.png*.

   ![image](https://github.com/ZuanAce/Security_BlueTeam_Challenge/assets/147037911/cf1fb344-313a-40ee-a067-db0859801001)

4. Open the file. It is an image containing the office locations.
   
   ![image](https://github.com/ZuanAce/Security_BlueTeam_Challenge/assets/147037911/8702d04a-ee72-49f9-8fde-e0c931e9a40e)

# Evidence 4
1. Navigated around the directories and found a suspicious file at the */WebDev work/unfinished webpages/templatemo_508_power/css* directory. Having studied web development courses in university, I couldn't help but notice a file that seemed out of place - bootstrap.min.abc. Typically, CSS files are used for styling websites and they have the .css extension. 

   ![image](https://github.com/ZuanAce/Security_BlueTeam_Challenge/assets/147037911/ebcdae87-5e79-43da-abef-d7be4a895621)

   ![image](https://github.com/ZuanAce/Security_BlueTeam_Challenge/assets/147037911/817ae334-c49a-4a9f-a5b1-26803c469f5a)

2. Within the css directory, use the command *cat bootstrap.min.abc* to display the contents within the file. It was found that Colin's information was leaked. 
   
   ![image](https://github.com/ZuanAce/Security_BlueTeam_Challenge/assets/147037911/39976359-955c-47ea-a721-d907e20adfc6)

# Answers to the Challenge
1. When considering the order of volatility, which is the MOST volatile form of evidence?
   - Cache
     
2. What is the Chain of Custody in regard to electronic evidence?
   - Paper trail for evidence that shows where it has been, and who has been in possession of it.
     
3. An employee is under investigation, and you are sent to look at his laptop. You discover that it is locked, but you have the user’s password to unlock it. What should you do next?
   - Wait for the user and get them to sign-in
     
4. Can social-media posts be counted as a form of electronic evidence?
   - Yes
     
5. Which one of the following evidence types holds the most value in court?
   - Real Evidence
     
6. When cracking ZIP passwords using fcrackzip, what are the flags used to conduct a brute force attack, with lowercase letters and numbers? format: -(flag) -(flag) (values)
   - -b -c a1
     
7. Digital Forensics mostly commonly entails…
   - The identification, preservation, and analysis of evidence found on electronic devices.
     
8. What does HTCIA stand for?
   - High Technology Crime Investigation Association
     
9. Computer Forensics and Data Recovery are the same thing, true or false?
   - False
     
10. Corporate Policies can dictate which of the following?
    - All of the above
    - 
11. [Evidence 1/4] What is the name of the file where the evidence was found? (filename and extension)
    - employeedump.txt
      
12. [Evidence 1/4] What is the name of the directory where this evidence was found?
    - to-do
      
13. [Evidence 1/4] What piece of evidence have you found?
    - Employee information

14. [Evidence 2/4] What is the name of the file where the evidence was found? (filename and extension)
    - laptop.jpg
      
15. [Evidence 2/4] What is the name of the directory where this evidence was found?
    - Images
      
16. [Evidence 2/4] What piece of evidence have you found?
    - List of employee passwords

17. [Evidence 3/4] What is the name of the file where the evidence was found? (filename and extension)
    -posidon.xml
    
18. [Evidence 3/4] What is the name of the directory where this evidence was found?
    - Week 10
      
19. [Evidence 3/4] What piece of evidence have you found?
    - Office Locations
      
20. [Evidence 4/4] What is the name of the file where the evidence was found? (filename and extension)
    - bootstrap.min.abc
      
21. [Evidence 4/4] What is the name of the directory where this evidence was found?
    - css
      
22. [Evidence 4/4] What piece of evidence have you found?
    - Colin Information

# Thanks for Reading!!
 

