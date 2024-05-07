# Introduction
This section discusses what steganography is and how Steghide can be used to hide or retrieve hidden messages.

# Steganography Activity and Quiz

1. Launch kali linux and then download the file.
2. Unzip the file using the command *unzip filename* replacing the filename with the name of the downloaded file
3. Navigate to SBT_Steg_Lab using the command *cd SBT_Steg_Lab*

   ![image](https://github.com/ZuanAce/Security_BlueTeam_Challenge/assets/147037911/818f103f-3eac-477f-89e2-7f1c4fff9547)

4. Use the command *ls -a* to list all files and directories, including hidden ones.

   ![image](https://github.com/ZuanAce/Security_BlueTeam_Challenge/assets/147037911/c1811709-db0a-4b52-aae2-13879893b781)

5. Run the command *steghide embed -ef secretmessage.txt -cf coverfile.jpg -sf hiddenmessage.jpg* to embed the file *secretmessage.txt* inside the cover file *coverfile.jpg* and name the output stegofile *hiddenmessage.jpg*.
   
   ![image](https://github.com/ZuanAce/Security_BlueTeam_Challenge/assets/147037911/481501c4-8cbd-4d60-9357-14a2dfaed314)

6. Navigate to Stego Files using the command *cd 'Stego Files'*. Using the command *ls* to list all the files withing the directory. There are 7 files to be sorted. Luckily, this is not a lot. If we had a huge amount of files to sort through, the StegDetect tool would have been used. It is a tool that detects steganographic content in images.

   ![image](https://github.com/ZuanAce/Security_BlueTeam_Challenge/assets/147037911/b025ab81-6973-4ee7-9c76-c51fa2eb98b3)

7. Using the command *steghide extract -sf filename* (replace the desired filename within the directory) to extract the embedded files for the flags. Through trial and error, I was able to find FLAG1.txt within the *pizza.jpg* file using the password *christmastree*. Using the *cat* command, I was able to retrieve the first flag *kAN105KS*.

   ![image](https://github.com/ZuanAce/Security_BlueTeam_Challenge/assets/147037911/7141da27-7232-4d08-918a-a6a41c29aa7e)

8. Repeat step 7 to find the remaining flag files. The second flag (*001JDANL*) was found within the *verypretty.jpg* file using the password *darksky123*. The third flag (*1LRBA9IU*) was found within the *car.jpeg* file using the password *goldenwatch*.

   ![image](https://github.com/ZuanAce/Security_BlueTeam_Challenge/assets/147037911/e4e90a71-33e6-431f-b290-2661fdc47e23)

   ![image](https://github.com/ZuanAce/Security_BlueTeam_Challenge/assets/147037911/f11ee7ec-e7a7-4c6a-a55b-14ff1fe680c2)


# Answers to the Quiz
**1. Embed the file 'secretmessage.txt' inside the cover file 'coverfile.jpg' and name the output stegofile 'hiddenmessage.jpg'. What is the full command you would use to do this?**
   
   - *steghide embed -ef secretmessage.txt -cf coverfile.jpg -sf hiddenmessage.jpg*
   
**2.  Flag 1 is hidden inside a text file in one of the steganography files. What is the value?**
   
   - *kAN105KS*
   
**3.  Flag 2 is hidden inside a text file in one of the steganography files. What is the value?**
   
   - *001JDANL*
   
**4.  Flag 3 is hidden inside a text file in one of the steganography files. What is the value?**
   
   - *1LRBA9IU*
   
















