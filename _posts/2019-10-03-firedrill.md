---
layout: article
title: The Big Hack - What did we learn?
categories: "articles"
image:
  teaser: finger.png
  thumb: finger.png
author: joefitz
---
Happy "The Big Hack"-iversary! What have we learned in a year? 


There are still divergent opinions about what actually happend here’s a bit of a refresher, plus some of my conclusions. Initially I was fascinated by the technical possibilies and quickly shared my thoughts:
<div class="jekyll-twitter-plugin"><blockquote class="twitter-tweet"><p lang="en" dir="ltr">There’s recent news about some really interesting hardware implants. I wanted to take a bit to share more technical thoughts and details that can’t be reduced to a mainstream article on the topic.<br />threaded: <a href="https://t.co/7VdmaDaQNr">https://t.co/7VdmaDaQNr</a></p>&mdash; Joe Fitz (@securelyfitz) <a href="https://twitter.com/securelyfitz/status/1047942844738981889?ref_src=twsrc%5Etfw">October 4, 2018</a></blockquote>
<script async="" src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>
</div>

I was asked repeatedly by people if they had hardware implants, so I summarized my answer:
<div class="jekyll-twitter-plugin"><blockquote class="twitter-tweet"><p lang="en" dir="ltr">Do I Have a Hardware Implant?<br /><br />I’ve gotten lots of inquiries if I could analyze some hardware for or could recommend someone who might. <br /><br />I’ll be blunt - most of you don’t need this. Here are some things you should consider before seeking out services like this:</p>&mdash; Joe Fitz (@securelyfitz) <a href="https://twitter.com/securelyfitz/status/1049415605164466176?ref_src=twsrc%5Etfw">October 8, 2018</a></blockquote>
<script async="" src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>
</div>

Way too many people spent those few weeks ripping apart servers looking for grain-of-rice sized malicious chips. When I saw this happening and took the time to stop think about it rationally, I realize that this was most certainly not a good use of resources.
At the time, I also shared the best TL;DR that I heard:
<div class="jekyll-twitter-plugin"><blockquote class="twitter-tweet"><p lang="en" dir="ltr"><a href="https://twitter.com/syncsrc?ref_src=twsrc%5Etfw">@syncsrc</a> said it to me best: <br /><br />TL,DR - if you haven’t talked to your vendors about the supply-chain integrity mechanisms they have in place, tearing down a few motherboards for analysis won’t solve your problems.</p>&mdash; Joe Fitz (@securelyfitz) <a href="https://twitter.com/securelyfitz/status/1049415623929819136?ref_src=twsrc%5Etfw">October 8, 2018</a></blockquote>
<script async="" src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>
</div>

Many of you owe thanks to @kimzetter and @riskybusiness who both convinced me to got on the record and share my dissatisfaction with the reporting. I have heard in the past year thanks from many people who felt the riskybusiness podcast saved them days or weeks of work searching for something that still hasn’t surfaced a year later.
<div class="jekyll-twitter-plugin"><blockquote class="twitter-tweet"><p lang="en" dir="ltr">I did a thing on the Bloomberg &quot;Big Hack&quot; story. <a href="https://twitter.com/securelyfitz?ref_src=twsrc%5Etfw">@securelyfitz</a>, one of the story&#39;s only named sources, warned the publication that its central claim &quot;didn&#39;t make any sense,&quot; prior to publication.<a href="https://t.co/giXVXo1tbF">https://t.co/giXVXo1tbF</a> <a href="https://t.co/6cnwuZGx99">pic.twitter.com/6cnwuZGx99</a></p>&mdash; Patrick Gray (@riskybusiness) <a href="https://twitter.com/riskybusiness/status/1049429881031819264?ref_src=twsrc%5Etfw">October 8, 2018</a></blockquote>
<script async="" src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>
</div>

I also spent some time theorizing about how and why the whole story came together, analyzing all of the details to see if they could fit together in a more realistic way. I never found the solution, but do check out my <a href="https://securinghardware.com/articles/big-hack-iversary/"> amateur, and likely incomplete anaysis.</a>

So What?
========
Over the past year, I've presented a few times and touched on several points that I feel are critical:

* Perhaps it's time to consider hardware differently in your threat model.
* Focus on your threat model. Don't waste your budget protecting someone else's threat model.
* $1M hardware and supply chain attacks sound cool, but don't waste resources on them if you're not protecting against $5 attacks.


October 4, 2018 was a firedrill.
================================
Who passed or failed the firedrill? Who took steps to adequately prepare for the actual fire when it happens?

Are you better prepared today for a supply chain attack than you were a year ago?

Have you had conversations with your suppliers about what they do to ensure authenticity?

If a report came out today that a specific silicon manufacturer had a supply chain issue - how long would it take you to confidently confirm whether or not you have any of that manufacturer's silicon?

How have you revised your threat model in the past year to consider hardware and supply chain attacks?
