---
layout: default
title:  "Blog 1"
nav_order: 3
parent: Blog Series
last_modified_date: "22-05-10"
---

# Blog 1 - Routine

I believe having a routine is important when learning new skills. A routine can help create consistency and develop healthy habits which supports your learning. That's why in this blog post, I will begin by talking about my daily routine for improving my InfoSec skillset and then talk about some of the 'miscellaneous' tasks that I've been working on since the last blog post. By the end of this blog, you will gain an understanding of the amount of work that I put in, so even if you aren't following exactly what I'm doing, you will gain an understanding of the workload for progressing into the InfoSec industry.

**What is covered in this blog:**

* Recap
* My routine for developing the areas of the five pillars
* Other related tasks I completed during the week

**What knowledge you will gain from this blog:**

* Understanding workload for developing InfoSec skills
* My personal routine and resources I use regularly
* Other tasks I'm working on that aren't in my routine

## Recap

The purpose of this recap is so that you know some of the prerequisite skills and resoruces that I assume you have before reading this blog. In blog 0, we talked about the five pillars, how I am tackling these pillars including resources I'm using, and a summary of my homelab. 

This blog covers week 3 CS50 problem sets, codewar exercises, packet tracer labs, offensive security video resources and a little about WatchGuard firewall setup. With this in mind, I am assuming that you have:

```markdown
1. Began working through Harvard's CS50
2. Started working through at least one of the python resources outlined in blog 0
3. Have a basic understanding of Cisco networking by starting Jeremy's CCNA series on YouTube
```

All the resources I recommend for starting are located in Blog 0, so make sure to check it out if you don't meet the assumptions listed above.

## Different Ways of Learning

At this stage you might be thinking, "I have all these resources, but how do I actually go about learning?" There are four different methods that I use when learning. Three of them I believe to be critical if you want a career in IT, and one that I strongly recommend you do. I will explain my process for learning each of the materials mentioned in this blog once I cover them later on.

The first way is to learn by doing! When working through these materials, make sure you are actively learning by completing the tasks whether it's coding exercises, trying out new attacks in your lab, configuring routers/switches in Packet Tracer or completing problem sets. There will be times where you get stuck. Use google, videos, course materials after you understand what you're trying to achieve. 

The second way is learn by watching. This includes videos, lectures, and if you're lucky enough, by watching a mentor/colleague. When watching videos, think about what the overall picture is and the key concepts that are being taught in the video. I find that it's easy to piece information together if I have a goal in mind **before** watching a video. For example, if I get stuck configuring a Cisco router as a Router on a Stick then I will watch the appropraite video with the goal of understanding how to reproduce that configuration.

The third way (and last critical way), is to learn by reading. This is important in the IT industry as you will often need to read Documentation or User/Administration Guides. Again, I find it helpful to have a specific goal in mind before reading about a topic. For example, if I need to write a for loop in C, or troubleshoot a specific issue then it's easier to pay attention and retain the information.

The last way is writing. I strongly suggest this as you will often need to write documentation in IT, and being able to communicate complex topics to someone with no knowledge helps you to gain a deeper understanding of the topic.

## My Routine

In this section I will break down resources I use daily categorised into the five pillars, when necessary. I will talk about the process I use when learning these topics so that you can start to build a complete picture of how I approach each resource. These tasks were completed between blog posts, which in this case was one week. All following blog posts will follow a similiar structure. You can see when each blog was last modified by viewing the footer of each blog. 

### Programming

My programming routine currently consists of two activities. The first is completing problem sets in Harvard's CS50 course, and the second is doing challenges on CodeWars. I start each workday by squeezing out 30 minutes of CodeWars challenges (when I'm not working on tickets), focusing only on Python. These challenges are just completing one a function that performs a particular task. Let's take a look at one example. 

[![](../CodeWars_Blog1.PNG)](../CodeWars_Blog1.PNG)

Here, our task is to write a function that will take one input, an integer, and return the expanded form of that integer as a string. Take a second to think about how we might go about solving this. 

We may think, let's iterate over each digit and multiple that digit by a factor of 10, depending on where it is. Take 17 for example, we iterate over the 1 first, multiple that by 10^1 to get 10, and then take the 7 and multiple that by 10^0 to get 7. Then just convert them into strings and add a '+' symbol between them. If you try this approach, you will find that you can't interate through type int. But if we turn that into a string first, now we can iterate through each digit. But we now need a way to track each iteration. How about we define a list and add each iteration mutiplied by a factor of 10? How do we know that factor of 10 for each digit? Lets define a counter variable that contains the length of the string. So for our example of input '17', we have a counter variable of 2, since len('17') is 2. If we decrease the counter by 1, then times the counter (which is an integer) by the string '0', we end up with a string of 0's equal to the amount of 0's that we need each place to be. 

Let's take input 123 as an example. We first convert that into a string '123', define the length of that string in a variable called counter, define an empty list, and then iterate over each character in the string. For the first character '1' we have the counter set to 3, since len('123') is 3. Decrease the counter by 1 to get 2, and multiply that by the string '0' to get the string '00'. We then concatenate the character '1' and the string '00' to get '100' and append that to our list. For the next character '2', counter is set to 2. We decrease it by 1, multiply the counter by '0' to get '0', concatenate character '2' and '0', and append to the our list. We now have [ '100' , '20' ]. 

This is what our code might look like at this stage:

```python
def expanded_form(num):
    s = str(num)
    counter = len(s)
    lst = []
    
    for i in s:
        counter -= 1
        lst.append(i+counter*'0')
```

We aren't done just yet though. We still need to join this list into a string and add an '+' symbol between each entry. I will leave this part up to you. If you are interested in code walkthroughs like this, make sure to check out the code walkthrough section on this site. 

Moving on to CS50, I completed Week 3 which touched on algorithms and continuing on with programming in C. I always start a new CS50 week by reading the first problem set assignment. This allows me to pick up what may be important to know when I go back and watch videos. If the the problem set has a walkthrough video, I watch that to gain a better understanding of the problem and tasks I need to complete in the assignment. Then I start doing the assignment by reading through the code and completing the TODO items laid out. If I get stuck I refer back to the short lecture videos in that week. I don't watch the big two hour lectures that they have for each week. If you learn by taking notes, I recommend you watch these lectures. I personally like learning when I know there's a specific problem that I need to solve, so watching shorter videos suits me better. 

This was a hard week. I completed Plurality and Runoff assignments. Plurality was fairly straight forward once you know how to work with arrays in C (covered in Week 2), Runoff was difficult. Be on the lookout for a Runoff walkthrough, as there is a lot of valuable information to discuss for that one. 

### Networking

My networking routine consists of working on Packet Tracer Labs for at least 30 minutes a days. This is a great way for getting experience working with the command line of Cisco devices, and practicing for the CCNA if you don't have physical equipment. My appraoch when learning Jeremy's CCNA content is to first download the flashcards for the day I'm working on, complete those until I can remember the answer to each flashcard (this sometimes takes a few goes), watch the day's lecture video, and then complete the day's lab using the lecture as a reference if I get stuck. Only watch the day's lab video after you have completed or given the lab a try first. Since I've completed all the videos and labs, I am building out one big lab that will contain all the labs provided by Jeremy's labs.  

To give a brief overview of what I've done so far, I implemented five VLAN's, three of which connected to two Layer 2 switches, which is connected to a router. Each of the three VLANs can route between each other using Router on a Stick (ROAS) configuration. The other two VLANS are connected to a Layer 3 Switch, which performs inter-VLAN routing. All five VLANs contain two host PCs each. Each device has IP addresses and subnets configured for their interfaces, when appropriate. The below image will give you an overview of the current topology. 

[![](../PT_Blog1.PNG)](../PT_Blog1.PNG)

### Videos

The last part of my routine consists of watching at least one video related to hacking Capture The Flag challenges, or Penertration Testing. I want to improve my programming skills a bit more before I take on some CTFs from sites as HackTheBox, TryHackMe and PicoCTF (and start including these in my blog!), but these videos are great to see the approach that others with much more experience take when solving these boxes. 

I'm currently watching John Hammond's CTF videos on YouTube and working through TheCyberMentors Practical Ethical Hacking course. The first half of the course is available on YouTube and provides a great introduction into Ethical Hacking, but if you want the fun stuff (Active Directory hacking) then you can buy the course on the [TCM Security](https://academy.tcm-sec.com/courses) website. 

These videos are more so to have fun and gain a big picture idea on the tools and methodology used in the Offensive Security field. 

## Non-Routine Tasks

In this section I just want to quickly add some other tasks I've done and provide resources so you have a more diverse range of learning materials. 

This week I was tasked to activate and do a basic set up for a WatchGuard firewall. With the networking knowledge I've obtained through the CCNA materials, most of what I've learnt was translatable to the set up of the WatchGuard firewall. I began reading through the [Network Essentials Study Guide](https://learn.watchguard.com/course/network-security-course) designed for the WatchGuard certification, which is a great resource for obtaining a WatchGuard certification. I recommend sticking to the CCNA, but you can use this if you're in an environment that uses WatchGuard equipment. Some of the topics can also provide a refresher for what you will be learning in the CCNA. 

I have also been planning on writing some network documentation, which won't be covered in this blog series. For those that already have an IT job, identifying what can be improved upon and getting approval to make such changes provides a great learning experience. Even if you aren't in the industry yet, create a lab and start playing around and seeing what things do, how they can break and how to fix them. So be on the lookout for anything that can be improved and plan out how to go about making those improvements. 

## Conclusion

In this blog post we covered ways of learning, what my routine looks like and provided some additional resources that you can start using. You now should have a rough idea on my workload and how to approach the materials covered in this blog post. Make sure you are actively doing the courses and tasks if you are following along with this series, and be on the lookout for any problems that you can solve, whether that's in a work or lab environment. 

Thanks for reading, and I will see you in the next blog!

<span class="fs-4">[Blog 0](/blog0.markdown){: .btn }</span> | 