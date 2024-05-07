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
1. Launch kali linux and then download the file.
2. Unzip the file using the command *unzip filename* replacing the filename with the name of the downloaded file
3. Navigate to *J Harrison Disk Image 10.09.2019* using the command *cd 'J Harrison Disk Image 10.09.2019'*

   ![image](https://github.com/ZuanAce/Security_BlueTeam_Challenge/assets/147037911/7c3ece5d-84c0-4d36-98ae-5906c0b5dee2)


5. Using the command *fcrackzip -b -u BruteForceAttack.zip* to conduct a bruteforce attack against *BruteForceAttack.zip*. Here's a breakdown what the command mean:
   - fcrackzip – Selecting the tool we want to use.
   - -b – Selecting the option for a brute-force attack.
   - BruteForceAttack.zip – The file we want to brute-force.
   - -u – This makes sure fcrackzip actually tries to unzip the file, without this we won’t actually get the right password.

   ![image](https://github.com/ZuanAce/Security_BlueTeam_Challenge/assets/147037911/78861b16-1a36-45b9-9623-35e60d876416)

6. However, the bruteforce attack took so much longer compare to dictionary attack. Using the command *fcrackzip -D -p /usr/share/wordlists/rockyou.txt -u BruteForceAttack.zip*, I was able to retrieve the password: *a1b3c5*

   ![image](https://github.com/ZuanAce/Security_BlueTeam_Challenge/assets/147037911/b3c72c02-e979-4a0f-bb58-db3bf4944088)

7. Using the password *a1b3c5* and the command *unzip BruteForceAttack.zip*, FLAG1.txt was extracted.

   ![image](https://github.com/ZuanAce/Security_BlueTeam_Challenge/assets/147037911/6e218ee2-ea1b-4a88-b014-c7b3972656c5)

8. Using the command *cat FLAG1.txt*, the flag value *J201AKKLO* was obtained.

   ![image](https://github.com/ZuanAce/Security_BlueTeam_Challenge/assets/147037911/2fc9f92d-e8ca-4725-b77e-7032d071d96b)

9. Using the command *fcrackzip -D -p /usr/share/wordlists/rockyou.txt -u DictionaryAttack.zip* to conduct a dictionary attack against *DictionaryAttack.zip*. The password is *FRIENDSHIPSTARS*. Here's a breakdown what the command mean:
   - fcrackzip – Selecting the tool we want to use.
   - -D – Selecting the option for a dictionary attack
   - -u – This makes sure fcrackzip actually tries to unzip the file, without this we won’t actually get the right password.
   - /usr/share/wordlists/rockyou.txt – This is the location of our wordlist, required to perform a dictionary attack.
   - DictionaryAttack.zip – The file we want to crack.
     
   ![image](https://github.com/ZuanAce/Security_BlueTeam_Challenge/assets/147037911/8aace566-b821-44f9-8d6a-8c332b899d76)

10. Using the password *FRIENDSHIPSTARS* and the command *unzip DictionaryAttack.zip*, FLAG2.txt was extracted.
   
   ![image](https://github.com/ZuanAce/Security_BlueTeam_Challenge/assets/147037911/e56fc698-ac47-427c-97a0-1d8ee1a1c389)

11. Using the command *cat FLAG2.txt*, the flag value *91MDOQL11* was obtained.

    ![image](https://github.com/ZuanAce/Security_BlueTeam_Challenge/assets/147037911/ee1d8264-282e-42eb-91a1-8b6f2c1fb539)



 

