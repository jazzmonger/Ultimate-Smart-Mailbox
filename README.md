# Smart-Mailbox
## 👋 Really Smart Mailbox

This all started when we moved to the country and getting the mail became a war of who/when/how far.  We run a business and getting checks deposited in a timely manner can mean the difference in making payroll or not.  So there's a vigil of constantly walking the 1/4 mile to the mailbox to see "if" the mail had arrived.  My wife wore me down, and I finally finished the project. It seems to work really, really well, and I solved many of the challenges the vast majority of all other solutions overlooked. Namely:

  - door open/closed monitoring is ineffective.  Both my wife and I put outgoing mail in the box, sometimes multiple times a day. this results in false triggers.
  - how to discern between outgoing mail and legitimate delivered mail?
  - we have a big mailbox. it holds several packages sometimes. how do you detect a small letter in a big box?
  - the box is 1/4 mile walk. I'm not keen on loRa long range solutions. They over complicate things.
  - Batteries are challenging.  Standard Lithium batteries wont work when its below freezing which it is here 6 mos out of the year.

So,those are the PRDs and challenges. I'll address each one.

## Detection:
I decided to use tof (time of flight) laser distance sensors. Ive had really good luck with them measuring pellet levels in both my pellet stoves. Initially I tried to measure from the top down. this proved impossibke as the resolution wasnt good enough to detect a post card or single letter.  But placed in the bottom so they are covered when there mail and using more than one sensor for a big box proved to be the answer here. These sensors draw some power so I had to figure out a way to put them in standby. Easier said than done.

## Outgoing vs incoming mail: 
Luckily our route uses the flag on the box to indicate outgoing mail only, so putting a sensor of the flag solves this issue.  Flag upp, theres outgoing mail.  Flag down, there is "potentially" incoming mail.

## Distance to mailbox: 
Fortunately I have Ubiquity AP's on the outside if my shop.  I can barely get a signal on my iphone standing at my mailbox. Choosing an ESP32 with an external ant connector and using a high gain ant proved the right solution. I have 100% connect rate during each wake cycle.

## Battery Choice: 
Lithium ion doesnt charge below freezing. LifePO4 batteries do diwn to -40F. So I use 2 single LifePO4 cells in parallel.  After over 2500 cycles theyve dropped from 3.4v to 3.29v. So, really quite good.Time will tell on battery life, but I have a few tricks here that really make a huge difference in extending battry life. Im also planning on adding a camera solar charge panel as soon as the LifePO4 chahrge modules are available again from Adafruit.

Ill expand on each of these areas in the Discussions sections as they all warrant much further deep dives. 
