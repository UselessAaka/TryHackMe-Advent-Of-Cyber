## Day 18

We first use top to view all the processes running and after that we will use 'sudo kill' to kill the process.

![image](https://github.com/UselessAaka/TryHackMe-Advent-Of-Cyber/assets/148384618/8733a6b9-1dab-471c-8c62-f9e8e6930fa0)

But we see that the process is still running even after we have killed it. Now to proceed further we will enter the process directory and list all the files.

![image](https://github.com/UselessAaka/TryHackMe-Advent-Of-Cyber/assets/148384618/d1fbb35f-e337-416e-aa38-4f4c15c6d90f)

We will read files like environ, cmdline, etc. and kan see in the cmdline ' unkillableproc'.

![image](https://github.com/UselessAaka/TryHackMe-Advent-Of-Cyber/assets/148384618/7ad5ae08-d7c2-43d6-805e-87944e2aa1da)

we will now list all files with having word kill in them.

![image](https://github.com/UselessAaka/TryHackMe-Advent-Of-Cyber/assets/148384618/1567480e-4ac0-4d82-98e7-e455104a7a3e)

Now here we will stop a-unkillable from running,

![image](https://github.com/UselessAaka/TryHackMe-Advent-Of-Cyber/assets/148384618/73edd310-7ce6-4187-8ef5-5d270092f070)

Also if we use 'top' command now, we won't see 'a' running.To save us from stopping it again we will just disable this process and also remove its files and directories.

![image](https://github.com/UselessAaka/TryHackMe-Advent-Of-Cyber/assets/148384618/e59697cd-40bd-46b0-aec4-5f8cf5e986ed)











