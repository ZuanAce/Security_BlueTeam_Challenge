# Introduction
Google dorks, or Google hacks, are specific search queries that you type in the Google search. In return, Google presents you with targeted search results. With Google dorks, you can search for key phrases or topics in specific websites, find specific file types, cached versions of web pages, and more. Here are some of the activities that I have done to try out Google Hack. 

# Activity

# Finding Files
Using the command *Cyber Security filetype:pdf* to instruct Google to search for PDF files containing the keywords "Cyber Security".

![image](https://github.com/ZuanAce/Security_BlueTeam_Challenge/assets/147037911/87b69aad-dd0d-4755-899e-47e4ec16e313)

# Subdomain Enumeration
The Google search query *site:Facebook.com -site:www.Facebook.com* is a combination of search operators used to specify the search scope within the Facebook domain while excluding specific subdomains. The result of the query is as shown below:

![image](https://github.com/ZuanAce/Security_BlueTeam_Challenge/assets/147037911/28b47b72-0287-4244-891f-09d9ec1927db)

# Keyword Searching

Using the Dork inurl: (value) we can look for specific keywords in a much more refined way than normal google searches. Using the query *inurl: admin* we can see a number of what appears to be admin login portals. This would be great if we were working as an attacker (if in scope, we can brute force or bypass the login portal to access administrator dashboards) or a defender (we can work to secure these portals so they are not compromised).

![image](https://github.com/ZuanAce/Security_BlueTeam_Challenge/assets/147037911/3382f562-fcbe-4623-b030-bcea287041c2)

# Log Files

The Google search query "allintext:username filetype:log" is a combination of search operators that can be used to find log files containing the term "username."

![image](https://github.com/ZuanAce/Security_BlueTeam_Challenge/assets/147037911/abeee9bf-6289-4fe0-bd13-a208726a9079)


# Resources
- https://securitytrails.com/blog/google-hacking-techniques
- https://nordvpn.com/blog/google-hacks/#:~:text=Google%20dorks%2C%20or%20Google%20hacks,of%20web%20pages%2C%20and%20more.
- https://github.com/chr3st5an/Google-Dorking
- https://www.searchenginejournal.com/google-search-operators-commands/215331/

