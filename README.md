# DC1 Vulnhub Walkthrough

#### Description
DC-1 is a purposely built vulnerable lab for the purpose of gaining experience in the world of penetration testing.

It was designed to be a challenge for beginners, but just how easy it is will depend on your skills and knowledge, and your ability to learn.

To successfully complete this challenge, you will require Linux skills, familiarity with the Linux command line and experience with basic penetration testing tools, such as the tools that can be found on Kali Linux, or Parrot Security OS.

There are multiple ways of gaining root, however, I have included some flags which contain clues for beginners.

There are five flags in total, but the ultimate goal is to find and read the flag in root's home directory. You don't even need to be root to do this, however, you will require root privileges.

Depending on your skill level, you may be able to skip finding most of these flags and go straight for root.

  
  # Scaning
  
  ### Reconnaissance 
  
![Screenshot from 2023-01-16 01-16-55](https://user-images.githubusercontent.com/108471951/212977979-8eb9986d-cfe5-43c1-94aa-c37492e289ed.png)

Firstly we have to identify the machine IP address using tool like NetDiscover [Command = Sudo NetDiscover]

### Nmap

![Screenshot from 2023-01-17 23-48-32](https://user-images.githubusercontent.com/108471951/212979611-b732a639-bb5c-40b0-a1b5-463c7ed54654.png)

nmap -sV 192.168.0.119 (service version scan)
