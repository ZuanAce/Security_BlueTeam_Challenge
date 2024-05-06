# Introduction
This section introduces the Linux command-line interface, including how to navigate the file system, how to read files, and how to identify files with incorrect extensions.

# Linux CLI Activity and Quiz

1. Launch kali linux and then download the file.
2. Unzip the file using the command *unzip filename* replacing the filename with the name of the downloaded file
3. Navigate to SBT_Linux_CLI-2 using the command *cd SBT_Linux_CLI-2*

   ![image](https://github.com/ZuanAce/Security_BlueTeam_Challenge/assets/147037911/ff6de136-4412-4f46-9be6-3f4bd5341f74)

4. Use the command *ls -a* to list all files and directories, including hidden ones.

   ![image](https://github.com/ZuanAce/Security_BlueTeam_Challenge/assets/147037911/0a873f86-05dd-4a46-902c-21b724633159)

5. The first text file to come across is *asdafada.txt*. Thus, using the command *cat asdafada.txt*. The command *cat* is used to concatenate files and display their contents. The phrase on line 8 of the file is *there's a snake in my boot*.
   
   ![image](https://github.com/ZuanAce/Security_BlueTeam_Challenge/assets/147037911/fa5d9b1c-9adb-41b4-a498-aafccf3e2725)

6. Navigate to /Home/PersonalFiles/Photos/ directory using the command *cd Home/PersonalFiles/Photos* and then, use the command *ls -a* to list all the files and directories, including hidden ones. There are *3 image files*.

   ![image](https://github.com/ZuanAce/Security_BlueTeam_Challenge/assets/147037911/0664749d-20d0-4a79-bb3f-5074f78eab79)

7. Just to be sure they are image files, run the command *file** to see their file types.

   ![image](https://github.com/ZuanAce/Security_BlueTeam_Challenge/assets/147037911/21754f8b-133d-4e43-b009-23b69071075f)

8. Using the command *cd ..* twice to navigate back to the home directory.

   ![image](https://github.com/ZuanAce/Security_BlueTeam_Challenge/assets/147037911/ac8fe11e-a769-4a03-b498-1cd1f9deb236)

9. Using the command *ls -a* to list all the files and directories.
    
   ![image](https://github.com/ZuanAce/Security_BlueTeam_Challenge/assets/147037911/fa2239d2-973d-49d4-baa9-ad0a63582fbc)

10. Using the command *file** to see all the file types within the directory. There are two files with the wrong extension namely *doggo.zip* and *pancakerecipe.txt*.
    
    ![image](https://github.com/ZuanAce/Security_BlueTeam_Challenge/assets/147037911/4a59c297-ac4c-4f5e-8dc1-c4527b041db9)
    
11. Using the command *mv doggo.zip doggo.jpg* to move the original file to the same location, but change the name to *doggo.jpg*. Same command is applied for *pancakerecipe.txt*.

    ![image](https://github.com/ZuanAce/Security_BlueTeam_Challenge/assets/147037911/c14169fc-a932-4900-8cb9-fe9d4218d9f8)
    
    ![image](https://github.com/ZuanAce/Security_BlueTeam_Challenge/assets/147037911/838dbcb4-7b57-463d-8d7e-2d316de1cdbb)

12. Checked both files and noticed the pancakerecipe.png has a secret message in it: SIERRA ECHO CHARLIE ROMEO ECHO TANGO

    ![image](https://github.com/ZuanAce/Security_BlueTeam_Challenge/assets/147037911/19155f80-15b1-4bc6-9d3b-aa6424fefb2f)

13. Navigate to this file path /SBT_Linux_CLI-2/Home/PersonalFiles/WorkStuff a text file that contains the string *bankdetails* can be found

    ![image](https://github.com/ZuanAce/Security_BlueTeam_Challenge/assets/147037911/83ec14b1-4237-487a-9bfe-ea0efe781253)

14. Using the command *ls -a* to list the hidden directories. The hidden directory is *.Private*. Navigate to the hidden directory, and use the *ls -a* command again to list all the files and directories if available. There is a *readme.txt* file. Using the *cat readme.txt* command to display the contents of the txt file. The flag value was found : *106019BAL0S0A1*.

    ![image](https://github.com/ZuanAce/Security_BlueTeam_Challenge/assets/147037911/db64b223-7c84-4c93-9b2e-2fbd7691e68d)

# Answers to the Quiz
**1. What is the phrase on line 8 of the first text file you come across?**
   
   - *there's a snake in my boot*
   
**2. There are two files with incorrect extensions, what are their filenames? (Without the file extensions, in the format: filename1 filename2**
   
   - *doggo pancakerecipe*
   
**3. One of these incorrect extension files hides a message, what is it?**
   
   - *SIERRA ECHO CHARLIE ROMEO ECHO TANGO*
   
**4. There is a text file with the string "bankdetails" as part of the filename. What is the full filename? (Including file extension)**
   
   - *11_09_2019_statement_bankdetails.txt*
   
**5. How many images are in the /Home/ directory? (Including files that SHOULD be images, if any)**
   
   - *5*
   
**6. What is the flag value inside the text file within the hidden directory?**
   
   - *106019BAL0S0A1*















