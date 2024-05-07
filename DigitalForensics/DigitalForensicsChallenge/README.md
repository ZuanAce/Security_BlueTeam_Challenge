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
