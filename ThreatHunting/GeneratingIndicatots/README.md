# Challenge Scenario
Now that you know how to make IOC files using Mandiant IOC Editor, it’s time to put your new skills to the test!
This activity will have you gathering IOCs from a number of files to make sure you understand everything we’ve covered so far. Remember, this is crucial so you can conduct your malware hunt later in the course. Below are the questions you’ll have to answer when you start the quiz, make sure you have your answers ready.

Download the ZIP file containing the four files for analysis below – We suggest you download this to your Kali VM to make use of Linux commands to retrieve MD5 and SHA-1 hashes.

# Approach
# File Beginning With “1”
1. What is the SHA1 hash value of this file?
   
   Used the command *sha1sum 1HIGHLY_MALICIOUS.txt*. The SHA1 hash value is **1f221ebaee912b351ec703874f3a0aa8a019dfd9**.
   
   ![image](https://github.com/ZuanAce/Security_BlueTeam_Challenge/assets/147037911/06ba2882-3e42-4a1b-b710-55e1ee41ef81)

2. What is the MD5 hash value of this file?
   
   Used the command *md5sum 1HIGHLY_MALICIOUS.txt*. The MD5 has value is **cf49367f7c184ee0a9ec7bc8c1ba907f**.
   
   ![image](https://github.com/ZuanAce/Security_BlueTeam_Challenge/assets/147037911/489d0158-4f15-4be3-b595-a3b7885c6253)

3. What is the file size (in bytes, with no separators such as “,”) of this file?

   Right click on the file, then select *Properties*. The file size is **86 bytes**.

   ![image](https://github.com/ZuanAce/Security_BlueTeam_Challenge/assets/147037911/10c14d91-2e0f-4930-b60e-f7e431f0e455)

4. What is the full file name (and extension) of this file?

   Using the same screenshot as above, the full file name of this file is **1HIGHLY_MALICIOUS.txt**.

# File Beginning With “2”
1. What is the SHA1 hash value of this file?
   
   Used the command *sha1sum 2innocent.pdf*. The SHA1 hash value is **90ffd2359008d82298821d16b21778c5c39aec36**.

   ![image](https://github.com/ZuanAce/Security_BlueTeam_Challenge/assets/147037911/59046b21-bef5-43c0-9b34-4afccecc2556)

2. What is the MD5 hash value of this file?
   
   Used the command *md5sum 2innocent.pdf*. The MD5 has value is **2942bfabb3d05332b66eb128e0842cff**.

   ![image](https://github.com/ZuanAce/Security_BlueTeam_Challenge/assets/147037911/5a109263-5cc6-4e23-aae0-e94c25702710)

3. What is the file size (in bytes, with no separators such as “,”) of this file?

   Right click on the file, then select *Properties*. The file size is **13264 bytes**.

   ![image](https://github.com/ZuanAce/Security_BlueTeam_Challenge/assets/147037911/e724903d-1a34-4329-b98f-f623840edea2)

6. What is the full file name (and extension) of this file?

   Using the same screenshot as above, the full file name of this file is **2innocent.pdf**.

# File Beginning With “3”
1. What is the SHA1 hash value of this file?
   
   Used the command *sha1sum 3Stock-Image-PANIC.jpg*. The SHA1 hash value is **0ecd0e0a47d3a2a9e9a9c835994963f8f20ae191**.

   ![image](https://github.com/ZuanAce/Security_BlueTeam_Challenge/assets/147037911/7aea72be-9f44-4314-b3da-9a1d52e8e8d2)

2. What is the MD5 hash value of this file?
   
   Used the command *md5sum 3Stock-Image-PANIC.jpg*. The MD5 has value is **3136fe5f1e43d07e8b509bbf710f5f31**.

   ![image](https://github.com/ZuanAce/Security_BlueTeam_Challenge/assets/147037911/acdd25c1-1fd0-4077-bb6d-f096febef8b4)

3. What is the file size (in bytes, with no separators such as “,”) of this file?

   Right click on the file, then select *Properties*. The file size is **1066208 bytes**.

   ![image](https://github.com/ZuanAce/Security_BlueTeam_Challenge/assets/147037911/3546d4d4-2209-4c02-9830-45d3f890a0ec)

4. What is the full file name (and extension) of this file?

   Using the same screenshot as above, the full file name of this file is **3Stock-Image-PANIC.jpg**.

# File Beginning With “4”
1. What is the SHA1 hash value of this file?
   
   Used the command *sha1sum '4sales report july 2019.pdf'*. The SHA1 hash value is **bc371bb75b9cbbec7819292bc3a380df913111be**.

   ![image](https://github.com/ZuanAce/Security_BlueTeam_Challenge/assets/147037911/84099a4b-f068-4526-966d-b5c869005266)

2. What is the MD5 hash value of this file?
   
   Used the command *md5sum '4sales report july 2019.pdf'*. The MD5 has value is **daa5ffbcc4f371070fb8b17e87b747e6**.

   ![image](https://github.com/ZuanAce/Security_BlueTeam_Challenge/assets/147037911/a0336bc2-2fa8-469c-a1fb-26926382dddc)

3. What is the file size (in bytes, with no separators such as “,”) of this file?

   Right click on the file, then select *Properties*. The file size is **43002 bytes**.

   ![image](https://github.com/ZuanAce/Security_BlueTeam_Challenge/assets/147037911/27ffa221-e4db-4b11-a113-85cbaac1b126)

4. What is the full file name (and extension) of this file?

   Using the same screenshot as above, the full file name of this file is **4sales report july 2019.pdf**.

# Additional Questions
Familiarise with Mandiant Editor and you can solve the questions easily!
1. In IOCe, when trying to add new IOC values, what is the first property available under the Network heading? (Similar to how we selected FileItem properties)
   
   Answer: Network DNS
   
   ![image](https://github.com/ZuanAce/Security_BlueTeam_Challenge/assets/147037911/6c5318d6-e1ef-480f-9c23-f04512989963)

3. In IOCe, there are option to add values from email, Snort, and Task Items, true or false?

   Answer: True

   ![image](https://github.com/ZuanAce/Security_BlueTeam_Challenge/assets/147037911/fff2d3ff-376c-4275-a1db-504517c4be8e)

4. What does IOC stand for?

   Answer: Indicators of Compromise

5. Which of the following are examples of IOCs? (Choose any that apply)

   Answer: Email Sending Address, IP Address, File Hash, String, Website URL

