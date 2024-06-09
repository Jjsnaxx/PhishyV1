<h2>Investigation - PhishyV1</h2>


<h2>Scenario:</h2>

You have been sent a phishing link - It is your task to investigate this website and find out everything you can about the site, the actor responsible, and perform threat intelligence work on the operator(s) of the phishing site.

Warning: The website and kit you see is the lab is REAL. Exercise caution when interacting with the malicious website and do not enter any sensitive information.



<br />

<p align="center">
  
<h2>Questions:</h2>

Q1. The HTML page used on securedocument.net is a decoy. Where was this webpage mirrored from, and what tool was used? (Use the first part of the tool name only) (4 points)

- The question is asking about securedocument.net. We navigate there to investigate and this is the landing page.
<img src="https://i.imgur.com/IX6fajP.png" height="80%" width="80%" alt="after.jpg"/>

- Looks to be a broken link. I right click and view page source.
<img src="https://i.imgur.com/mtxn7TC.png" height="80%" width="80%" alt="after.jpg"/>

Answer: 61.221.12.26/cgi-sys/defaultwebpage.cgi, httrack

<br />
<br />

Q2. What is the full URL of the background image which is on the phishing landing page? (3 points)

- On the instance desktop there is a text document 'phishy v1 readme'. We navigate to the link in the file. securedocument.net/secure/L0GIN/protected/login/portal/index1.html?1614546319649
<img src="https://i.imgur.com/o0NYpsT.png" height="80%" width="80%" alt="after.jpg"/>

- The question is asking for the full URL of the background image. Right-click and select copy image link.

Answer: http://securedocument.net/secure/L0GIN/protected/login/portal/axCBhIt.png

<br />
<br />

Q3. What is the name of the PHP page which will process the stolen credentials? (3 points)

- View page source.
<img src="https://i.imgur.com/sGGmuYE.png" height="80%" width="80%" alt="after.jpg"/>

- Next to form action we can see the php page.

Answer: jeff.php

<br />
<br />

Q4. What is the SHA256 of the phishing kit in ZIP format? (Provide the last 6 characters) (3 points)

- I tried scouring through page sources of both page sources for a zip file. No luck. I then did some research on how to traverse a web page. Much like a folder I can ascend in the directory.  I navigate to "http://securedocument.net/secure/L0GIN/protected/login/" which results in:
<img src="https://i.imgur.com/ufCl2IC.png" height="80%" width="80%" alt="after.jpg"/>

- I continue moving up the parental directory searching for the zip file. Until I reach http://securedocument.net/secure/
<img src="https://i.imgur.com/srWilc2.png" height="80%" width="80%" alt="after.jpg"/>

- I download the zip file and run it through sha256sum.

Answer: fa5b48

<br />
<br />

Q5. What email address is set up to receive the phishing credential logs? (3 points)

- Going back to question 3. The php page that will process the credentials. Jeff.php If we click on that we can see who the recipient will be.
<img src="https://i.imgur.com/ImdqE4T.png" height="80%" width="80%" alt="after.jpg"/>


Answer: boris.smets@tfl-uk.co

<br />
<br />

Q6. What is the function called to produce the PHP variable which appears in the index1.html URL? (3 points)

- This one was a little trickier for me. Ended up going through the all directories and viewing page sources but couldn’t find anything. So I had to navigate the directory through the page source to find my answer.
<img src="https://i.imgur.com/qf5NHDR.png" height="80%" width="80%" alt="after.jpg"/>
<img src="https://i.imgur.com/HVA83F8.png" height="80%" width="80%" alt="after.jpg"/>

Answer: getTime()

<br />
<br />

Q7. What is the domain of the website which should appear once credentials are entered? (3 points)

- Once again we navigate to jeff.php.
<img src="https://i.imgur.com/btGSyEp.png" height="80%" width="80%" alt="after.jpg"/>

Answer: office.com

<br />
<br />

Q8. There is an error in this phishing kit. What variable name is wrong causing the phishing site to break? (Enter any of 4 potential answers) (3 points)

- The username and password are assigned different variable names on the main page.
<img src="https://i.imgur.com/a3iSmmB.png" height="80%" width="80%" alt="after.jpg"/>
<img src="https://i.imgur.com/paeXSlp.png" height="80%" width="80%" alt="after.jpg"/>

- In the jeff.php form it is expecting variables user1 and pass1.

Answer: pass1










<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
