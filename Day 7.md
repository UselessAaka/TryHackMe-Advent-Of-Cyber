## Day 7

First we will go to the directory using 'cd Desktop/artefacts/' and there we will do 'ls -lah' where l is for detailed info of files, a is for showing hidden files, h for human readable format.
Now we will use 'head access.log' where head prints the first 10 lines of the specified files.

![image](https://github.com/UselessAaka/TryHackMe-Advent-Of-Cyber/assets/148384618/af496473-6828-4777-9337-d78855cd3de6)

Now we will use 'cut -d ' -f2 access.log | sort | uniq -c | sort -n | wc -1' and we can count and get the first answer 9.

![image](https://github.com/UselessAaka/TryHackMe-Advent-Of-Cyber/assets/148384618/eab34b96-b511-45b8-a454-eb6c8ceeb779)

### Flag
> 9

Now we will use the command 'cut -d ' ' -f3 access. log | cut -d ':' -f1 | sort | uniq -c | sort -n | wc -1' to see how many unique domains were accessed by the workstations.

![image](https://github.com/UselessAaka/TryHackMe-Advent-Of-Cyber/assets/148384618/a277f9d4-e29c-45dc-8867-793e42795b92)

### Flag
> 111

For the next question we will use ' cut -d' ' -f3,6 access. log | grep partnerservices' and we can see that it is returning a 503 error.

![image](https://github.com/UselessAaka/TryHackMe-Advent-Of-Cyber/assets/148384618/87e92bfb-8e9b-4c73-b215-a24f1237c218)

'cut -d ' ' -f3 access.log | cut -d ':' -f1| sort | uniq -c | sort -n' this will give us the domain with most connection attempts.

![image](https://github.com/UselessAaka/TryHackMe-Advent-Of-Cyber/assets/148384618/a2b75aaf-062f-405a-bf82-0af855d7f906)

### Flag
> frostlings.bigbadstash.thm

' cut -d -f2,3 access.log | grep frostlings.bigbadstash.thm' will be used to get the ip address

![image](https://github.com/UselessAaka/TryHackMe-Advent-Of-Cyber/assets/148384618/5614511f-865b-4eb3-810f-4d737e8050cb)

' cut -d -f2,3 access.log | grep frostlings.bigbadstash.thm | wc -l ' will give us the count of how many requests were made by this domain.

![image](https://github.com/UselessAaka/TryHackMe-Advent-Of-Cyber/assets/148384618/a8f62e8e-d543-4663-9629-4f1e72b4dcf1)

Now lastly we will use 'grep frostlings.bigbadstash.thm access. log | cut -d ' ' -f5 | cut -d '=' -f2 | base64 -d' an then we have to search the flag format 'THM{...}' in the data given which will be our answer.

![image](https://github.com/UselessAaka/TryHackMe-Advent-Of-Cyber/assets/148384618/70c92beb-029c-4a48-8dff-15bc5f574b1e)
