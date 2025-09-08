# [Fake Bank Writeup](https://tryhackme.com/room/offensivesecurityintro)

- Briefing: Our goal is to find a way to hack the FakeBank application to steal money. For that purpose, they have provided us with an account in the bank, just as if we were a regular user. One of the easiest ways we can try to hack the application is by finding hidden features in the application. Sometimes, applications will expose sensitive functionality to users via secret URLs. If we can find such URLs, we might be able to perform actions that a regular user is not supposed to do. To find hidden URLs, we will use a tool called dirb. This tool uses a brute-force approach, by taking a list of potential page names and testing one by one if they exist in your website. This approach works because people use predictable names a lot of times.

```bash
ubuntu@tryhackme:~/Desktop$ dirb http://fakebank.thm

-----------------
DIRB v2.22    
By The Dark Raver
-----------------

START_TIME: Mon Sep  8 18:30:35 2025
URL_BASE: http://fakebank.thm/
WORDLIST_FILES: /usr/share/dirb/wordlists/common.txt

-----------------

GENERATED WORDS: 4609                                                          

---- Scanning URL: http://fakebank.thm/ ----
+ http://fakebank.thm/bank-deposit (CODE:200|SIZE:4663)                        
+ http://fakebank.thm/images (CODE:301|SIZE:179)                               
                                                                               
-----------------
END_TIME: Mon Sep  8 18:30:42 2025
DOWNLOADED: 4609 - FOUND: 2
```

The output of the command might look a bit intimidating, but here's a simple breakdown of what is reported:

The first section of the output tells us the URL_BASE we scanned, which is just the URL we gave the tool. It also shows the location of the wordlist file used by the tool, which contains common page names that will be tested during the brute-force attack. In this case, the tool uses the default wordlist included with the tool, located at /usr/share/dirb/wordlists/common.txt. There's a copy of the common.txt file in your desktop as well, if you want to explore it.
The lines starting with a + sign are the results of the scan. In this case, dirb was able to find two URLs for you. Try opening them in the machine's browser! You might find something interesting.

http://fakebank.thm/bank-deposit
http://fakebank.thm/images

You should have found a secret page that allows you to add funds to a bank account (http://fakebank.thm/bank-deposit). Type the hidden page into the FakeBank website using the browser's address bar.
From this page, you should be able to add funds to your bank account (remember your bank account number is 8881). Let's add $2000 to it:
If you managed to add $2000 or more to your account, you should be able to see your new balance reflected on your account page. Press the Return to Your Account button at the end of the deposit receipt to go there now and confirm you got the money!
