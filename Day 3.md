## Day 3
After understanding how password and brute forcing them works we will start the attackbox. After opening the terminal we will run the command 'crunch 3 3 0123456789ABCDEF -o 3digits.txt' which will basically list all the possible # digits passwords from (0123456789ABCDEF) and write it in a txt file. 

![image](https://github.com/UselessAaka/TryHackMe-Advent-Of-Cyber/assets/148384618/a4036388-fd9c-44cb-8e70-2317108ed12d)

Now we have to see the source code of the website given and find for 'http://MACHINE_IP:8000/login.php' and then come back to the terminal and run the command 'hydra -l '' -P 3digits.txt -f -v MACHINE_IP http-post-form "/login.php:pin=^PASS^:Access denied" -s 8000'. We will let it test the passwords and at last get the password that is '6F5'.

![image](https://github.com/UselessAaka/TryHackMe-Advent-Of-Cyber/assets/148384618/c6da698d-8a1f-4e23-b7fe-9edb10a1e49c)

We will go back to the website and type in the password and continue.

![image](https://github.com/UselessAaka/TryHackMe-Advent-Of-Cyber/assets/148384618/d14a9c20-49da-448e-985c-e11720bd3831)

There we will see an option open door and we will click it to get the flag.

![image](https://github.com/UselessAaka/TryHackMe-Advent-Of-Cyber/assets/148384618/7d8637d4-3354-4198-a6d9-c3f1e9dcdbf4)

### Flag
> THM{pin-code-brute-force}
