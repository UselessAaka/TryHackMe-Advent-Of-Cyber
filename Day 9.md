## Day 9
After readng all the info we will open dnspy in the virtual machine and open the file from Desktop in the folder artefacts  after thta we have to enter JuicyTomatoy then its exe file then program and then lastluy in postit to find which HTTP User-Agent was used by the malware for its connection requests to the C2 server.

![image](https://github.com/UselessAaka/TryHackMe-Advent-Of-Cyber/assets/148384618/41845e50-b343-43df-9207-9f2a7c2e9ef7)

#### Flag
> Mozilla/5.0 (Macintosh; Intel Mac OS X 14_0) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/17.0 Safari/605.1.15

And now second question is about telling which HTTP method is used to submit the command execution output, so we can see it is 'POST'.

![image](https://github.com/UselessAaka/TryHackMe-Advent-Of-Cyber/assets/148384618/1674ddeb-b22b-43ef-8a76-4043714eb5b1)

For third question, the key used by the malware to encrypt or decrypt the C2 data is found in the encryptor file .

![image](https://github.com/UselessAaka/TryHackMe-Advent-Of-Cyber/assets/148384618/219aeb7e-c2cc-4c46-bac2-3a5bf22d994c)

#### Flag
> youcanthackthissupersecurec2keys

Now we will go in the "Main" to get the 4th answer .

![image](https://github.com/UselessAaka/TryHackMe-Advent-Of-Cyber/assets/148384618/475a825a-129f-4cec-b7a9-37caad61d551)

#### Flag
>

Now for 5th we need to get the 'int count' which is 15000 but sleep takes in milliseconds so it is 15 seconds.

![image](https://github.com/UselessAaka/TryHackMe-Advent-Of-Cyber/assets/148384618/c7ff9c26-21dc-4cc7-b0a8-06aec985dbfe)

We can see that in the 'Main' code we are using shell command .

![image](https://github.com/UselessAaka/TryHackMe-Advent-Of-Cyber/assets/148384618/1f93927c-bee0-4e44-b9b1-49ece4a50cd6)

For 5th ques we need to find the domain used by malware to download another binary so implant will be used so if we go down in the 'Main' program we can url for implant and there is the flag.

![image](https://github.com/UselessAaka/TryHackMe-Advent-Of-Cyber/assets/148384618/f11db145-cbb3-406e-a960-91e2339359ba)

#### Flag
> stash.mcgreedy.thm
