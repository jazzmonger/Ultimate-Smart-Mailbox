# Ultimate Smart Mailbox
## 👋 Really Smart Mailbox

![IMG_0898](https://github.com/user-attachments/assets/589818ac-c647-4411-996b-f8bd7c9f2783) ![image](https://github.com/user-attachments/assets/d22fc5bf-06ad-4461-b9f1-45b5aef52140)
![image](https://github.com/user-attachments/assets/7ef88d97-25d6-4b1b-8b45-2d1d94712f97)
![image](https://github.com/user-attachments/assets/d06128d1-f7f8-444b-920e-5a9b431a2094)
![image](https://github.com/user-attachments/assets/e15b5274-1175-4aa9-9c47-7a3dac161b37)

This all started when we moved to the country and getting the mail became a war of who/when/how far.  We run a business and getting checks deposited in a timely manner can mean the difference in making payroll or not.  So there's a vigil of constantly walking the 1/4 mile to the mailbox to see "if" the mail had arrived.  My wife wore me down, and I finally finished the project. It seems to work really, really well, and I solved many of the challenges the vast majority of all other solutions overlooked. Namely:

  - door open/closed monitoring is ineffective.  Both my wife and I put outgoing mail in the box, sometimes multiple times a day. this results in false triggers.
  - how to discern between outgoing mail and legitimate delivered mail?
  - we have a big mailbox. it holds several packages sometimes. how do you detect a small letter in a big box?
  - the box is 1/4 mile walk. I'm not keen on loRa long range solutions. They over complicate things.
  - Batteries are challenging.  Standard Lithium batteries wont work when its below freezing which it is here 6 mos out of the year.

So,those are the PRDs and challenges. I'll address each one.

## Detection:
I decided to use tof (time of flight) laser distance sensors. Ive had really good luck with them measuring pellet levels in both my pellet stoves. Initially I tried to measure from the top down. this proved impossible as the resolution wasnt good enough to detect a post card or single letter.  But placed in the bottom so they are covered when there mail and using more than one sensor for a big box proved to be the answer here. These sensors draw some power so I had to figure out a way to put them in standby. Easier said than done.

## Outgoing vs incoming mail: 
Luckily our route uses the flag on the box to indicate outgoing mail only, so putting a sensor of the flag solves this issue.  Flag upp, theres outgoing mail.  Flag down, there is "potentially" incoming mail.

## Distance to mailbox: 
I can barely get a wifi signal on my iphone standing at my mailbox. Choosing an ESP32 with an external ant connector and using a high gain ant proved the right solution. I have 100% connect rate during each wake cycle.

## Battery Choice: 
Lithium ion batteries don't like to charge when it's below freezing. LifePO4 batteries do, all the way down to -40F. So I use 2 single 1000ah LifePO4 cells in parallel.  After over 2500 cycles they've dropped from 3.4v to 3.29v. So, really quite good.  Time will tell on battery life, but I have a few tricks here that really make a huge difference in extending battery life. Im also planning on adding a 5v/5w camera solar charge panel as soon as the LifePO4 charge modules are available again from Adafruit.

I might even add a camera inside so the wife can see all the packages she's gotten from Amazon.  Oh wait... That's for me :)

<img width="1019" alt="image" src="https://github.com/user-attachments/assets/dfdec941-0bc4-4731-8959-b0a08b416819">

Ill expand on each of these areas in the Discussions sections as they all warrant much further deep dives. 
https://github.com/jazzmonger/Smart-Mailbox/discussions

