## Day 2

After understanding all the basics of jupyter notebooks. Now we will use 'df.count()' where df is datframe which basically can be thought of as a table with rows and columns. It will give us the count of packet numbers, timestamps,etc.

![image](https://github.com/UselessAaka/TryHackMe-Advent-Of-Cyber/assets/148384618/f00e19bd-e2d0-448f-b887-130da8e5ddae)

### Flag
> 100

Now according to next question we have to tell the IP address that sent the most amount of traffic during the packet capture and for that we can see which IP address has how much traffic by using 'df.groupby(['Source']).size()'. 

![image](https://github.com/UselessAaka/TryHackMe-Advent-Of-Cyber/assets/148384618/4e1fb6cb-655a-4fa1-bc2c-888f1cfffed8)
### Flag
> 10.10.1.4

Now we have to tell the most frequent protocol and we can do similar thing we did in the above quesion that is 'df.groupby(['Protocol']).size()'.

![image](https://github.com/UselessAaka/TryHackMe-Advent-Of-Cyber/assets/148384618/d81e46ab-2e5e-4f53-b350-ee57412cbdc6)

### Flag
> ICMP
