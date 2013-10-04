---
layout: post 
root: "./.." 
author: Matt Mets
category: post
tags: 
type: 
img: blog 
title: Tiny LED Controller and the Cheapest Buttons, Ever
technologies: 
when: 3/19/2013
collaborators: 
task: 
desc: 
context:  
---

![LED Controller](/images/{{page.img}}/led1.jpg)

When I saw this tiny LED controller on Taobao for only RMB10 (about $1.60 USD), I had to know what was inside of it. Less than 12 hours after clicking buy, it arrived at our office. Of course, the first thing I had to do was tear it apart to see what was inside.

The first thing to notice is the packaging, or lack thereof. It’s literally a piece of heat shrink tubing molded around a small PCB, with a sicker stuck to the one side. Note: this is totally something you could do at home, and makes for a quick, dust-free housing. Add some silicone glue around the wires and you’re water resistant, too!

![LED Controller](/images/{{page.img}}/led2.jpg)

Cutting off the heat shrink cover reveals a minimalist PCB underneath. The top side has pads on the edges with power and data wires (no connectors here!), along with a STC15F101E microcontroller (RMB1.5 on taobao), and a couple of passives. Pretty standard. Note the 2×3 row of vias that make a nice connection between the ground trace on the top of the board to the ground plane on the back.

![LED Controller](/images/{{page.img}}/led3.jpg)

On the back is an awesome surprise: super cheap buttons! These are nothing more than tiny, stamped little metal discs, that pop down when you press them to short out two parts of a PCB. They’re actually just taped in place, and you can peel them up:

![LED Controller](/images/{{page.img}}/led4.jpg)

That’s super slick, and probably also super cheap. It probably won’t last forever, either, but we aren’t exactly talking about a luxury product here.

Edit: This style of button is called 锅仔片 (Guō zǎi piàn, or metal dome), and they are also super cheap- around RMB.01 ($.0016 USD) each in quantities of 1000. Thanks, Honghong!

![LED Controller](/images/{{page.img}}/led5.jpg)

The final step was to hook it up and see if it actually works. This particular controller can only support WS2811-style LED drivers, and I didn’t happen to have any on hand, so I soldered it up to an integrated WS2811 pixel instead. Lo and behold, it lights up and changes color! I’ll have to reserve judgement on the animation quality until I get a full set of strips, but I’m not expecting much more than blinking and color fading patterns from it. Improving this state of affairs is, of course, one of the main reasons that we started Blinkinlabs.
