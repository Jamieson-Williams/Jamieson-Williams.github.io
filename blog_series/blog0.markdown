---
layout: default
title:  "Blog 0"
nav_order: 2
parent: Blog Series
---
# Blog 0 - The Initial Blog

This is where it begins. Welcome to the very first blog in this series of My Journey to an InfoSec Career. 
If you want to know more about what this blog series is all about, head over [here](/about). 
Before we begin I just want to say that this blog post will only contain a summary of what I've done up to this point in my journey. Future blog posts will contain more specific information where you can follow along and see exactly what I'm doing!

Now, let's discuss what this initial blog will include. 

### The Five Pillars Explained

The idea of this blog is to explain what is known as the 'Five Pillars of an InfoSec Professional' and what I've learnt regarding these five pillars. Since deciding to enter the IT field, more specifically the IT Security field, I've been working on honing my skills in these five areas. The five pillars are known as the 'basics' or the foundational skills that you need to have a solid understanding in to be a proficient InfoSec professional. The five areas are:
```markdown
  1. General Computing
  2. Computer Networking
  3. Scripting and Programming
  4. Linux/MacOS
  5. Windows
```
Let's briefly explain what each pillar means. 

### General Computing Explained

The general computing pillar refers to the basics of computer science and how computers work. You will want to understand what each component of a computer is designed to do, what is a thread, what is a process and what does the term caching mean, for starters. 

### Computer Networking Explained

The computer networking pillar is all about how devices communicate and send data to each other. This is a huge topic to understand for any IT professional. Having a solid understanding of the OSI model, VLANs, subnets, routing tables, protocols such as DHCP/DNS/ARP and the role networks play in securing the IT infrastructure will enhance your skills as an InfoSec professional. 

### Scripting and Programming Explained

The scripting and programming pillar refers to being able to create simple scripts to automate tasks. It's important to learn how to read and understand what code is attempting to do so you can secure it (or exploit it!).

### Linux/MacOS Explained

The linux/MacOS pillar mentions being able to navigate the linux Operating System using the command line. Understanding permissions, software installation/maintenance and various commands will make it easier to interact with the various tools used to enumerate networks and bypass security protections.

### Windows Explained

The windows pillar is being able to explain how various windows functions work. Some of these functions include the registry, UAC, DLLs and Tokens. Being able to maneuver through the OS only using the command line and possessing basic PowerShell abilities is esssential. 
Take your time to read through this post of the [5pillars](https://github.com/DFIRmadness/5pillars/blob/master/5-Pillars.md). This is your reference to understanding the key foundational areas that will help you start your career in InfoSec!

### My Current Experience

We now have a starting point with lots of references, but how am I going about learning this overwhelming amount of information? Well, let's break down each pillar one by one. 

### General Computing

The first steps I took when tackling this pillar was to learn the Comptia A+. Do I recommend that you should take the A+? No. Am I A+ certified? Also no. The A+ provides a good introduction into the world of computers and IT but you don't need to be certified. I used Professor Messer's youtube videos to learn about how computers work, and what each component in a computer does. Aso note that I have built a few computers which can help assist in learning about each component. This is not important for landing an InfoSec job, but can be very fun!

### Computer Networking

For learning networking, I follow the exam objectives outlined by the CCNA. The CCNA gives fantastic foundational network knowledge, and also teaches you how to configure core devices that are responsible for moving data. The resources I'm using include:
```markdown
  Jeremy's IT Lab on youtube, which comes with free Cisco Packet Tracer labs and flashcards to aid in my studies
  Understanding Cisco Networking Technologies written by Todd Lammle
  Boson ExSim Practice Exams
```
I have finished all of Jeremy's youtube videos and labs. I am currently redoing the labs using the book Understanding Cisco Networking Technologies as a guide. Labbing is very important if you want to fully understand the material and take the CCNA exam, which is something I'm planning on doing. In addition to CCNA studies, I have set up a homelab and a pfSense virtual router using VMWare virtualisation. On the pfSense is mutiple subnets to divide the network, firewall rules, VPN configurations and more. Down below will have more info on my current homelab. If you are interested in looking at a diagram of my current homelab, head over to my [Github](https://github.com/Jamieson-Williams) and check out the homelab repository. 

### Scripting and Programming

There are a lot of different paths you can take to learn programming. A programming language should be seen as a tool, and the tool you pick depends on the work you will be doing. I started with Python, as this is highly recommended by others and a common language you will see in the InfoSec field. 
The first resource I used to get started was Automate the Boring Stuff with Python. Take your time absorbing the information and most importantly **DO** the practice programs at the end of each chapter. I moved onto Python for Everybody after completing most projects in Automate the Boring Stuff with Python. Use the website [py4e.com](https://www.py4e.com/) over taking the Coursera (or any other online platform) course. This might be overkill as many of the topics you learn are also taught in Automate the Boring Stuff with Python. I found both resources to be very informative and help reinforce the concepts. Once I completed Python for Everybody, I moved onto Introduction to Computer Science using Python which is available at MIT OpenCourseWare. The problem sets are challenging and should not be skipped over. You will learn new concepts such as recursion, OOP and Sorting algorithms. 
In addition to learning python, I've also started to work through the well known course, Harvard's CS50. This course introduces programming in C, python, SQL and JavaScript. 
I have written a few basic Powershell scripts for work and try to leverage it whenever possible. My suggestion is to use Powershell as often as possible if you're working in an IT role (or any role where you can use Powershell). The suggested resource for learning Powershell is the book Learn Powershell in a month of Lunches, for those interested in digging deeper into Powershell. 

### Linux/MacOS

Learning Linux can be a daunting experience. This is because learning linux entails working at the command line. For most people, including myself, it's the first time at being at the command line. Luckily, there are a lot of resources out there to help nail the basics so you can start navigating around. I used a variety of resources to first learn the basics, and from there just continued to use only the command line when setting up Linux servers in my homelab. Some of the resources I used to learn the basics of linux include:
```markdown
  Linux Journey. Only completed the grasshopper modules. 
  OverTheWire Bandit. This is extremely fun. I recommend creating a folder for each level to store the key so you can come back and access the level you left at. Struggle and google around if you get stuck!
  The Cyber Mentor - Practical Ethical Hacking. Watch the Introduction to Linux module. This part is freely available on youtube. 
```

### Windows

This pillar has surprisingly been the hardest to learn. In the Scripting and Programming section you can see my recommendation on how to go about learning Powershell. But what about the other important windows features? For me, most of my learning has come through setting up Active Directory Labs (yes plural) and managing Active Directory in an enterprise environment. Active Directory could be it's own blog post (or series!), so instead I recommend finding a tutorial on how to set up a simple virtual environment (good opportunity to configure a virtual pfSense router), install a Windows Server Virtual Machine and install the Active Directory Domain Services role, promote it to a Domain Controller, and then install a Windows 10/11 VM and connect it to the domain. 
There is this awesome reddit post that provides a checklist of tasks you can do all within your virtual lab. I have completed all the tasks, and I highly recommend you to do the same! [Reddit post](https://www.reddit.com/r/sysadmin/comments/3z7qd9/practice_to_become_a_windows_sysadmin/cyjynxh/) 

Be on the lookout for these five pillars as we progress through the blog series. They will pop up a lot!

### A Small Note on my Homelab

Not all of my experience can be summarised within these five pillars. This section will give brief details about the work I've put into my homelab. I want to note that the experience I've gained and will talk about in this section is not directly tied to improving my InfoSec skillset. Instead, these are just fun projects I tinkered with. Maybe you will be inspired to do the same or research more about the technologies. Also, to avoid this blog post being too long, I will skim over the details of each VM and setup. That could be coming in a new blog series!

### My Homelab

At the center of my homelab is the pfSense router. This segregates all three of my subnets, not allowing broadcast traffic to pass, making each subnet more efficient. The router provides connectivity between the subnets if they need to send data through each other. If you don't understand why or how subnets don't pass broadcast traffic, use the resources in the Computer Networking section! PfSense is also configured with port forwarding (NAT) rules, ACLs for different subnets, two VPNs, pfBlockerNG and snort. 
One of my subnets holds all of my Linux servers. All servers are installed as a core installation, meaning there is no Graphical Interface, only a command line. I have two DNS servers using BIND DNS, two IPA servers using FreeIPA and a Foreman server which also holds the puppetmaster role. Why two of the same servers? The first reason is redundancy. If one server goes down, I've configured the other to take control and ensure the service is available for the hosts. The other reason is to test and practice configuring replication between those servers. 
It is best practice to keep your Foreman and Puppetmaster service on a different server. That's one mistake I made when planning for deployment of these services, so if you want to implement this in your own homelab keep them separate! My github contains some puppet manifests that I've wrote, so check them out in my jamPuppet reposistory.
The second subnet consists of my linux hosts. Both VMs are running CentOS. Not much to say about this one. I use these machines to connect to the services (i.e my BIND DNS servers handle all DNS requests for these machine, while IPA servers handles the authentication) and to learn linux/bash commands. 
The last subnet holds my media server and files, sonarr which is installed in a docker container and also five vulnerable machines with a ParrotOS VM to practice penetration testing. All machines were downloaded from The Cyber Mentor's mid-course Capstone projects. This is the same course mentioned in the Linux/MacOS section, so check out the videos on youtube! 
In addition to the three subnets, pfSense is also configured with two VPNs. One of those connections to is NordVPN. The other uses an IPSec tunnel to a remote server. On that remote server has an Active Directory lab that was used to achieve all the tasks outlined in the linked reddit post from the Windows section. The server now provides a way to practice internal penetration techniques on the network that uses Active Directory. I hope to talk more about some of these attacks in future blog posts. 

### Conclusion

That was a long blog post, thanks for making it this far! You are now caught up to where I am currently at with my journey. If you are just getting starting in IT this is a lot to take in. Make sure to google any terms that you might not know and start learning the 5pillars from the resources detailed in this blog. Be patient and consistent with your studies and you will be surprised with how much you will learn.

Thanks for reading, and I will see you in the next blog!
