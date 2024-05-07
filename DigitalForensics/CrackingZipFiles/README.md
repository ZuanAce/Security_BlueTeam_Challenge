# Introduction
This section talks about password-protected files, and how they can be cracked with brute force or dictionary attacks.

# Cracking ZIP Files Activity and Quiz

1. Launch kali linux and then download the file.
2. Unzip the file using the command *unzip filename* replacing the filename with the name of the downloaded file
3. Navigate to SBT_Steg_Lab using the command *cd SBT_ZIP_Cracking*

   ![image](https://github.com/ZuanAce/Security_BlueTeam_Challenge/assets/147037911/650c9076-317b-427e-8e4d-ba07fc28a248)

4. Using the command *fcrackzip -b -u BruteForceAttack.zip* to conduct a bruteforce attack against *BruteForceAttack.zip*. Here's a breakdown what the command mean:
   - fcrackzip – Selecting the tool we want to use.
   - -b – Selecting the option for a brute-force attack.
   - BruteForceAttack.zip – The file we want to brute-force.
   - -u – This makes sure fcrackzip actually tries to unzip the file, without this we won’t actually get the right password.

   ![image](https://github.com/ZuanAce/Security_BlueTeam_Challenge/assets/147037911/78861b16-1a36-45b9-9623-35e60d876416)

5. However, the bruteforce attack took so much longer compare to dictionary attack. Using the command *fcrackzip -D -p /usr/share/wordlists/rockyou.txt -u BruteForceAttack.zip*, I was able to retrieve the password: *a1b3c5*

   ![image](https://github.com/ZuanAce/Security_BlueTeam_Challenge/assets/147037911/b3c72c02-e979-4a0f-bb58-db3bf4944088)

6. Using the password *a1b3c5* and the command *unzip BruteForceAttack.zip*, FLAG1.txt was extracted.

   ![image](https://github.com/ZuanAce/Security_BlueTeam_Challenge/assets/147037911/6e218ee2-ea1b-4a88-b014-c7b3972656c5)

7. Using the command *cat FLAG1.txt*, the flag value *J201AKKLO* was obtained.

   ![image](https://github.com/ZuanAce/Security_BlueTeam_Challenge/assets/147037911/2fc9f92d-e8ca-4725-b77e-7032d071d96b)

8. Using the command *fcrackzip -D -p /usr/share/wordlists/rockyou.txt -u DictionaryAttack.zip* to conduct a dictionary attack against *DictionaryAttack.zip*. The password is *FRIENDSHIPSTARS*. Here's a breakdown what the command mean:
   - fcrackzip – Selecting the tool we want to use.
   - -D – Selecting the option for a dictionary attack
   - -u – This makes sure fcrackzip actually tries to unzip the file, without this we won’t actually get the right password.
   - /usr/share/wordlists/rockyou.txt – This is the location of our wordlist, required to perform a dictionary attack.
   - DictionaryAttack.zip – The file we want to crack.
     
   ![image](https://github.com/ZuanAce/Security_BlueTeam_Challenge/assets/147037911/8aace566-b821-44f9-8d6a-8c332b899d76)

9. Using the password *FRIENDSHIPSTARS* and the command *unzip DictionaryAttack.zip*, FLAG2.txt was extracted.
   
   ![image](https://github.com/ZuanAce/Security_BlueTeam_Challenge/assets/147037911/e56fc698-ac47-427c-97a0-1d8ee1a1c389)

10. Using the command *cat FLAG2.txt*, the flag value *91MDOQL11* was obtained.

    ![image](https://github.com/ZuanAce/Security_BlueTeam_Challenge/assets/147037911/ee1d8264-282e-42eb-91a1-8b6f2c1fb539)


# Answers to the Quiz
**1. What is the working password to unlock BruteForceAttack.zip?**
   
   - *a1b3c5*
   
**2. What is the working password to unlock DictionaryAttack.zip?**
   
   - *FRIENDSHIPSTARS*
   
**3. What is the text string inside FLAG1.txt?**
   
   - *J201AKKLO*
   
**4. What is the text string inside FLAG2.txt?**
   
   - *91MD0QL11*

# Resources
- https://medium.com/@rajendraprasanth/password-cracking-using-kali-67e0b89578df
   

















