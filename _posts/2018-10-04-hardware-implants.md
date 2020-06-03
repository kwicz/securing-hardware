---
layout: article
categories: "articles"
image:
  teaser: finger.png
  thumb: finger.png
author: joefitz
---
There's recent news about some really interesting hardware implants. I wanted to take a bit to share more technical thoughts and details that can't be reduced to a mainstream article on the topic.

The core of the claim is that someone implanted extra components on some server motherboards that would do malicious stuff, subvert the system and possibly allow it to 'phone home'. I looked at the claims through a technical and feasibility lens.

I've studied hardware implants for a few years now. I've done multiple reviews of server hardware looking for backdoors. I profit, via @securinghw and @SecureHardware, from people being more interested in hardware security.

That's the extent of my knowledge. I have no specific information about the implants being reported on. I do feel like my background qualifies me to comment from a technical perspective.

First, how do we build a hardware implant?
==========================================

With hardware access, there are plenty of ways to backdoor a server. Someone knowledgable could quickly pick out a dozen well marked places malicious firmware could hide on a board and dozens of more components large enough to contain a capable implant inside them.

The biggest target is the BMC. It's trivial to modify the firmware of most BMCs, and many of them are trivial to exploit remotely because of the poor quality, outdated software they run. 

Most of the capabilities of the described attack could be implemented in BMC firmware, be just as stealthy, and be FAR lest costly to design and implement.

Moving beyond firmware modifications, we have a ton of chips on the system that communicate with each other. The BMC and more can give and receive commands over I2C/SMBUS. @gsuberland showed situations where you could send packets from I2C - and lots of things connect to I2C.

But I2C is a shared bus. Anyone on the bus can take control. Microcontrollers that can speak I2C cost pennies and are available in all sorts of packages. Most boards even have I2C bridges that might be customizable to be malicious.

Even if someone were careful enough to check every chip against known parts, we can hide stuff further. Capacitors are often big metal cylinders scattered all over the board. Visual and X-ray inspection would show - a capacitor. What if we stuff components inside though?

Chips are getting smaller. The manufacturing capabilities in china available to everyone - not just state-spectrum actors - is incredible. Want a microcontroller in a tiny package that is normally used for power or RF components? no problem.

Some people picked on the original article for describing a fully capable computer the size of a pencil point. That's still far fetched - but something the size of a pencil point that subverts the rest of the system to do that is feasible, today. Explain that to nontech audiences.

How do we know something is a hardware implant?
===============================================

With a little knowledge and healthy paranoia, it's easy to mistake something as a malicious hardware implant

There are lots of bold claims on the internet about backdoored hardware who are actually just finding engineering solutions to problems - for example, putting 2 pieces of silicon in a single package makes sense when one is flash storage and the other is a microcontroller.

But an inexperienced observer could easily jump to the conclusion that it's a hardware implant. Likewise, lots of small components these days are actually several components manufactured into a single package for ease of use.

If you really find an implant, are you sure that it's actually malicious? Plenty of counterfeit prevention (and counterfeit bypassing) modifications fit bill for malicious hardware implants - but they vary significantly in their profit motive.

Because of this, whenever I  hear someone say something about malicious hardware implants, i'm incredibly skeptical. And i'm someone whose business depends on and who spends most of their time trying to make people aware of how easy hardware attacks can be.

As an analogy, we're talking about designing and building a special screw that when used to build a suitcase, opens a secret side compartment when you knock on it just right - except that it's otherwise secured with a TSA lock that everyone has a key to.

When DO hardware implants make sense?
=====================================

I just told you how easy they are followed by how rare they are. When would someone use an implant?

The ANT catalog taught me that even though I'm a hardware person with hardware access and limitless capabilities - it makes more sense for hardware implants to grant software access/privilege, and then get out of the way. It's just more efficient.

There are plenty of software vectors for exploiting a system. None of them require silicon design, hardware prototyping, or manufacturing processes, and none of them leave behind a physical item once they're implanted.

Installing malicious software on 10,000 systems is a system management problem. Installing malicious hardware on 10,000 systems starts out as an HR problem and moves on from there. It's just not scalable.

How could we make a hardware implant scalable?
==============================================

First, it has to be cheap. But cheap microcontrollers cost pennies and are tiny. Solved.

Second, we'd have to hide it. We could build it in to another functioning component (expensive), or just find it in a package that *looks* like something more common. Solved.

Now, we need to get it on the board. This is the supply chain hack. Maybe we pay off a component supplier. Maybe we intercept component shipments. Maybe we intercept the design process of the board and spec it. But to make it cheap - it probably has to be added at manufacture time.

Now we need to get it to our target. Every board has it, but we probably only care about one targeted customer of the board. This is where it gets complicated. If 10 million backdoored motherboards all ping the same home server, everyone will notice. I don't have a solution here.

What do i think of the whole deal?
==================================

This could be an ANT Catalog moment, or it could be a BadBIOS moment. We have reporting on some pretty amazing capability used in a way we haven't seen before.

The @NSAPlayset explored what was possible with off the shelf versions of ANT catalog tools, and saw it was all entirely feasible for the general public - but years later. #radbios showed us some of the BadBIOS claims were feasible.

I'm confident there's some truth to the story. I am also confident that details get lost in translation. Even savvy software security experts fumble nuances in hardware details, so I can only guess what a real-world game of telephone looks like at the other end.

How would I make this implant?
==============================
At one point in time I had a conversation about how I would put a hardware implant into a system. I'm delighted to see @qrs had a very similar assessment:

<div class="jekyll-twitter-plugin"><blockquote class="twitter-tweet"><p lang="en" dir="ltr">Zooming in on the Bloomberg animation showing the alleged malicious component in the Supermicro servers looks reasonable for the described attack. It is positioned on an unpopulated SOIC-8 SPI flash footprint between the SOIC-16 SPI flash chip and the BMC. <a href="https://t.co/EdFweJk0EE">pic.twitter.com/EdFweJk0EE</a></p>&mdash; Trammell Hudson ⚙ (@qrs) <a href="https://twitter.com/qrs/status/1047910169261330432?ref_src=twsrc%5Etfw">October 4, 2018</a></blockquote>
<script async="" src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>
</div>

as did @marcan42:
<div class="jekyll-twitter-plugin"><blockquote class="twitter-tweet"><p lang="en" dir="ltr">Looking at the GIF in <a href="https://twitter.com/BW?ref_src=twsrc%5Etfw">@BW</a>&#39;s story about China putting hardware implants into Supermicro servers, it all looks reasonably realistic as a MITM on the BMC&#39;s SPI boot flash. I don&#39;t know how real the photo is supposed to be, though. <a href="https://t.co/eQxp5RsNG6">pic.twitter.com/eQxp5RsNG6</a></p>&mdash; Hector Martin (@marcan42) <a href="https://twitter.com/marcan42/status/1047806561760890880?ref_src=twsrc%5Etfw">October 4, 2018</a></blockquote>
<script async="" src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>
</div>

Given a photo of a server motherboard, this was my response after a few minutes. You'll have to take my word I wrote this 4 Sept 2017 - 13 months ago. I did make minor typographical fixes here:

*START OF QUOTE*

Well, you picked an easy one, it already has a backdoor :)
![annotated motherboard](https://pbs.twimg.com/media/DostcaDUUAEzUJN.jpg)

The ASPEED chip (1) is the BMC or Board Management Controller. It's an extra CPU on the system that is supposed to 'manage' the actual server that does all the work, like negotiating power supplies and storage connections with the rest of the servers in the rack.

The ASPEED chip is likely running an ancient, outdated linux kernel that has documented vulnerabilities. Even if it is not, it's entire firmware is stored on a simple 8 or 16 pin chip (2 or 3, most likely #3)

In the event that wouldn't work, the other chip (probably #2) is almost certainly the PC bios. You can add a bootkit that loads some code at boot and configures it to be run once the operating system has loaded.

There's a space (4) for yet another chip. From the looks of it it might be an alternate place for the PC bios (2) in case they wanted to cut costs and use an 8 pin part instead of a 16 pin part, but it could have a different purpose.

Lastly there are tons of testpoints (5) that could include a debug port to the board management controller, or could be to monitor the interface between BMC and the main CPU

My hardware attack scenarios in order: (assuming software were out of scope)
---------------------------------------------------------------------------

1. Modify the ASPEED flash chip to give a backdoor that can drop a payload into the host CPU's memory sometime after boot.
2. Modify the PC Bios flash chip to drop a bootkit backdoor into the OS sometime after boot.
3. Solder a device onto the board to intercept/monitor/modify the values read from the flash chip as they are accessed to inject malicious code somewhere
4. Find debug connections on the testpoints to allow debugger controll of the ASPEED BMC, allowing you to direct it to drop a payload into memory

I think that #4 would probably be the coolest illustration of the point. you could glue the microcontroller you've got upside-down to the top of the ASPEED chip, and then solder its legs to some nearby testpoints (AKA dead-bug-style soldering).

If you wanted the implant to look more discrete, you could place it on the spot labeled '4' but don't solder the legs down to those pads, instead run fine wires to testpoints. That would look more 'factory rework' than 'malicious implant'.

The more advanced attack is much more difficult an would require more than just an 8-pin micro controller. In the part below, there's 4 pairs of wires routed to the connector on the left with nothing on the right side - they're just not used.
![PCIe](https://pbs.twimg.com/media/DostT60VAAAgynj.jpg)

It would be conceivable to attach to those lines (almost certainly PCI Express) with a malicious device that could do direct memory attacks on the system as long as the OS doesn't properly enable those protections.

*END OF QUOTE*


Can you spot a hardware backdoor?
=================================
Also in 2017, i presented this slide w/ @r00tkillah a few times. These are supposed to be 'stateless' logic-only devices. Quad XOR on the right, microcontroller with code implementing a Quad XOR on the left. That also stores the last 1024 bits XORed. Can you tell the difference?

![logic](https://pbs.twimg.com/media/Dosxks4UcAA4aMU.jpg:large)

What's that thing in the picture?
=================================
Hector and others have identified the component used in the bloomberg article to represent the hardware implant. I'd like to share my perspective on whether it's realistically possible:

<div class="jekyll-twitter-plugin"><blockquote class="twitter-tweet"><p lang="en" dir="ltr">Left: <a href="https://twitter.com/BW?ref_src=twsrc%5Etfw">@BW</a>&#39;s supposed Chinese implant for Supermicro BMCs. Right: a TDK RF diplexer from a cell phone. Artist&#39;s conception, a *really* good disguise but for entirely the wrong product (you won&#39;t find these in a server), or fake news? Up to you. <a href="https://t.co/kdPZcfkodY">https://t.co/kdPZcfkodY</a> <a href="https://t.co/nlPvcBvwXc">pic.twitter.com/nlPvcBvwXc</a></p>&mdash; Hector Martin (@marcan42) <a href="https://twitter.com/marcan42/status/1047925500318965760?ref_src=twsrc%5Etfw">October 4, 2018</a></blockquote>
<script async="" src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>
</div>

If someone said that the implant was found inside a coupler, first I'd check component suppliers for couplers that might fit the bill. And the one displayed is pretty much the smallest one you can find with 'coupler' in the name.

But a package is a package. 
It is a single component, but it is assembled out of several pieces and has 6 pins.

Think of it as an ultra small pcb that you can customize.

You could get a coupler, mill out material on the bottom, glue a piece of silicon in there, and then wire bond it to the pads of the coupler. It'd be indescernable from the top when it's soldered in place. But that's slow and manual.

If you haven't already, you should watch Shenzhen: The Silicon Valley of Hardware. While it's not security focused, it gives a really good perspective on how stuff gets built in china.

<div class="video"><figure><iframe width="640" height="480" src="//www.youtube.com/embed/SGJ5cZnoodY" frameborder="0" allowfullscreen=""></iframe></figure></div>

You show up at the factory with a box of silicon and say 'package this for me' and you get it back next day. Or you show up with a bag of packaged chips, and say 'unpackage this silicon, and put it in a different package' Done.

You might see a bit more why creating a tiny hardware implant isn't actually that difficult when you've got open access to all of the manufacturing techniques. You should assume small scale and top secret techniques are several steps ahead of what's available on the open market.

Now, though, the flaws in the choice.
That's not a component you'd normally find on a motherboard. Finding it would be very suspicious.
There's lots of stuff on a motherboard. many of them are much larger and easier to hide inside or in place of.

@riskybusiness cited a source that saw a white chip with 8 pins. So when you're matching up lots of sources, the coupler might sound like a good choice.

I'm pretty sure sure the implant was NOT inside that tiny coupler. There's no doubt that the images are mock-ups for the article. But I'm also pretty sure that it's in the realm of what's technically possible today.


