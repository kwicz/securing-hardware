---
layout: article
title: The Big Hack - Disconnecting the Dots
categories: "articles"
image:
  teaser: finger.png
  thumb: finger.png
author: joefitz
---
Happy "The Big Hack"-iversary.

Last year I was as caught off guard as the rest of us when I saw this article in print. I was torn between defending that many of the claims were technically possbile versus challenging that the whole story fit together logically. I did a lot of reading and re-reading, and took these notes on the story to try and analyze what was actually going on.

I'm still sure there's some truth behind what happened, but I felt more and more confident that the dots just weren't getting connected properly. I hoped that I could find a theory that minimized the inconsistencies and didn't involve multiple intentionally misleading or malicious sources. I wrote most of the below notes in October 2018 but hadn't gotten around to organizing them to post.

I'll start by annotating each cited source and numbering them. Then, I'll sort out what each source provided. Last, I'll try to reconnect the dots in a way that makes more sense.


> To help with due diligence, AWS, which was overseeing the prospective acquisition, hired a third-party company to scrutinize Elemental’s security, according to one person familiar with the process.

Source #1 likely inside elemental or amazon

> In late spring of 2015, Elemental’s staff boxed up several servers and sent them to Ontario, Canada, for the third-party security company to test, the person says.

Still on the same source. Nothing this source provided seems untrue - or newsworthy. Security reviews happen all the time, and uncover 'troubling' issues all the time.

> Nested on the servers’ motherboards, the testers found a tiny microchip, not much bigger than a grain of rice, that wasn’t part of the boards’ original design.

This could still be source #1, but i'm going to go with #2. This still isn't necessarily newsworthy. Board changes, reworks, and revisions happen all the time. Just because analysis found a different chip doesn't mean it's a malicious backdoor.

> Multiple people familiar with the matter say investigators found that the chips had been inserted at factories run by manufacturing subcontractors in China.

This also could be the same sources as above, but it says multiple, so i'll assign them #3. Problem is, that source #3 is just telling us a known fact - chips are put on boards at factories in china.

> But that’s just what U.S. investigators found: The chips had been inserted during the manufacturing process, two officials say, by operatives from a unit of the People’s Liberation Army. 

'Officials' lead me to believe that this is a government source. They're saying that malicious chips have been inserted at manufacture by the PLA. This is not likely #1 or #3 because neither are really referenced as government like these. This could be #2, but that didn't cite 'multiple. Let's call this #4. We risk severing the link between the information from #2, but let's take that risk for now.

> One official says investigators found that it eventually affected almost 30 companies

Officials again. Could be one of the officials from above or a third one. Either way we'll call them source #5. Source #5 may be talking about something completely different from the previous paragraph.

> Three senior insiders at Apple say that in the summer of 2015, it, too, found malicious chips on Supermicro motherboards.

Sources #6 #7 and #8. All at apple. They should know what goes on at apple, but anyone who has worked at a large company might know that doesn't mean they know details of what happens in different departments/organizations. This one also could easily be a misreporting of finding malware in BMC firmware - while the dates don't line up perfectly, 2015 is when facebook allegedly heard about firmware issues, and we might assume apple heard the same info.

> The companies’ denials are countered by six current and former senior national security officials, who—in conversations that began during the Obama administration and continued under the Trump administration—detailed the discovery of the chips and the government’s investigation.

This might be #2, #4, and #5 we saw previously, as well as new sources #9, #10, and #11. I'm not sure on the wording here. Were these sources shown apples denials and said 'that's not true', or did they simply give information that - when connected as the story does - appear to contradict those claims.

> One of those officials and two people inside AWS provided extensive information on how the attack played out at Elemental and Amazon; 

I think this is probably #1 and #3 as insiders, and either #2 or #4 as the official. This isn't new information - it could be just enumerating what was said above

> the official and one of the insiders also described Amazon’s cooperation with the government investigation.

Here, one of the insiders and one of the officials noted above. I don't think it refers to a third amazon insider because of the wording.

> In addition to the three Apple insiders, four of the six U.S. officials confirmed that Apple was a victim.

A victim of what? This is insiders #6 ,#7, and #8, plus ONLY 4 of the 6 officials. So - 2 of them refuted apples statement, but DID NOT confirm apple was a victim. Were they asked and declined to state? Did they not know? Were they #2 and #4 that were more amazon-focused officials? I'm going to assume they were included in the 6 because of the way the dots connect.


> In all, 17 people confirmed the manipulation of Supermicro’s hardware and other elements of the attacks. 

We got up to 11, but some of those might be multiple people with similar statements. Some are likely sources from the other stories. There's only 6 to go though.

> One government official says China’s goal was long-term access to high-value corporate secrets and sensitive government networks. 

This is one of the 6 cited above - but doesn't say anything that's not an easy assumption to make, so i think it's irrelevant.

At this point the article goes on a tangent about supermicro, perhaps hinting we shouldn't trust them because many of them are chinese and speak mandarin.

> A U.S. official says the government’s probe is still examining whether spies were planted inside Supermicro or other American companies to aid the attack.

I don't know who this is of the 6, but let's use #9

> “Think of Supermicro as the Microsoft of the hardware world,” says a former U.S. intelligence official who’s studied Supermicro and its business model.

I'm going to make this #11 because they're a *former* official, the other 5 are perhaps current. The quote isn't subtantive to the story though.

> Well before evidence of the attack surfaced inside the networks of U.S. companies, American intelligence sources were reporting that China’s spies had plans to introduce malicious microchips into the supply chain. The sources weren’t specific, according to a person familiar with the information they provided

This is a second hand source. Doesn't count.

> But in the first half of 2014, a different person briefed on high-level discussions says, intelligence officials went to the White House with something more concrete: China’s military was preparing to insert the chips into Supermicro motherboards bound for U.S. companies. The specificity of the information was remarkable, but so were the challenges it posed.

This is a 'person' not an 'official' or 'insider' I'll go with #12. This doesn't specify rice-grain-sized chips. Malicious microchips could refer to silicon backdoors or firmware backdoors, when referring to the whole BMC. It woudln't surprise me if there was a heads up to the firmware incidents that came up in 2015 and 2016.
The specificity of the information doesn't have to refer to what the journalists were told - it could easily refer to the intel that was shared with the white house.

> Apple made its discovery of suspicious chips inside Supermicro servers around May 2015, after detecting odd network activity and firmware problems, according to a person familiar with the timeline.

Not an official or insider. Not sure this is a unique person, but we'll call them #13 for now. Suspicious chips could refer to lots of things - not necessarily rice-sized-implants. It could be something nonmalicous and still align with their strong denial, or it could be something like counterfeit components. That's a real, common, issue that might cause the issues.

> Two of the senior Apple insiders say the company reported the incident to the FBI but kept details about what it had detected tightly held, even internally. 

Nothing new to worry about here - one source just didn't mention the FBI. Of course they keep details tightly held - even more reason for those sources to be slightly mistaken/misinformed

> Government investigators were still chasing clues on their own when Amazon made its discovery and gave them access to sabotaged hardware, according to one U.S. official.

I would guess this is someone who had unique details about the AWS case, either #2 or #4. #4 previously talked about investigators so we'll assign that one.

> The chips on Elemental servers were designed to be as inconspicuous as possible, according to one person who saw a detailed report prepared for Amazon by its third-party security contractor, as well as a second person who saw digital photos and X-ray images of the chips incorporated into a later report prepared by Amazon’s security team.

Not insiders or officials, just people. Maybe #12 from above, less likely #13 since that person had apple information. I'm going to assign #14 to the second person, assuming #1 and #3 were insiders. Only one of them saw pictures, but we don't know which.

> “Hardware attacks are about access,” as one former senior official puts it.

Former official is probably #11 from above. This specific quote bothers me because it's something I say regularly. I don't have record of saying that exact quote in email, but i may have said it over the phone, and I know that I constantly say that hardware attacks are about using physical access to give software privilege. It's true though, so I can't disagree if a senior official says the same thing.

> In simplified terms, the implants on Supermicro hardware manipulated the core operating instructions that tell the server what to do as data move across a motherboard, two people familiar with the chips’ operation say.

We're running out of sources. Lets say #12 and #14 because they're 'people' and have seen reports of the chips that hopefully said what they do. I saw an early revision of this paragraph, though. It had no reference to 'people familiar' It quoted me at the end, and gave feedback on the technical flaws of the description. So i want to throw this out completely, because they didn't say it, but may have ok'd the language showed them.

>  To understand the power that would give them, take this hypothetical example: 

I explained DMA attacks that could be done with implants here. I'm not one of the 17 sources, i don't get a number :(

> U.S. officials had caught China experimenting with hardware tampering before, but they’d never seen anything of this scale and ambition.

No citation. Not a source, maybe sourced from another article?

> In order to get further down the trail, U.S. spy agencies drew on the prodigious tools at their disposal. They sifted through communications intercepts, tapped informants in Taiwan and China, even tracked key individuals through their phones, according to the person briefed on evidence gathered during the probe. Eventually, that person says, they traced the malicious chips to four subcontracting factories that had been building Supermicro motherboards for at least two years.

Back to #12 or #14, probably. The 'person' here seems to be one of the most knowledgable of the whole thing, and might be the main source fo the story.

> ...The middlemen would request changes to the motherboards’ original designs, initially offering bribes in conjunction with their unusual requests....
> The existence of this group has never been revealed before, but one official says, “We’ve been tracking these guys for longer than we’d like to admit.”

This official knows about a PLA group. Its unclear if they were the source of the info about middlemen. But how it went down was observed by an agent, maybe written in a report, which was read by this official and reported to a journalist. Lots can get lost in that translation - when none of them are likely to have a hardware background. I'll guess #10

> This project, known internally as Ledbelly, was designed to make the search function for Apple’s voice assistant, Siri, faster, according to the three senior Apple insiders.

insiders #6 #7 #8. perhaps everyone at apple knows this though? it's not exactly spy-chip-top-secret.

> Because Apple didn’t, according to a U.S. official, provide government investigators with access to its facilities or the tampered hardware, the extent of the attack there remained outside their view.

This is consistent with apple's denial - they didn't get access because there was nothing to investigate. I won't arbitrarily assign it to an official because it's not significant.


> Although the investigators couldn’t be sure they’d found every victim, a person familiar with the U.S. probe says they ultimately concluded that the number was almost 30 companies.

This info was previously attributed to an official, but now it's a person. A person reading an official report might have this info, and person #12 or #14 seem to fit the bill.

> One executive of a large web-hosting company says the message he took away from the exchange was clear: Supermicro’s hardware couldn’t be trusted. “That’s been the nudge to everyone—get that crap out,” the person says.

I'm going to call this #15. They're quoted and identified. Doesn't mean they weren't a 'person' listed previously but we can't know which. There's no detail about time of this message - could it be the same message facebook received, and maybe others too?

> ...according to one person familiar with Amazon’s deliberations... 
> ...in a transaction whose value one person familiar with the deal places at $350 million...
> ...according to two people with knowledge of AWS’s operations there...

More information from amazon from 'people', not insiders. I don't attribute them because they're nontechnical bits, and i don't believe they're disputed

>  In one case, the malicious chips were thin enough that they’d been embedded between the layers of fiberglass onto which the other components were attached, according to one person who saw pictures of the chips. 

This is a big deal. There's no other detail about this. It's also technically and logistically difficult, dramatically increasing the cost of PCBs in a way that might be easily detected by QA. again, this is a 'person' not an amazon insider, I'll put it on #12 or #14 again.

> Its security team determined that it would be difficult to quietly remove the equipment and that, even if they could devise a way, doing so would alert the attackers that the chips had been found, according to a person familiar with the company’s probe.
> ...Amazon decided to act, the person familiar with the company’s probe says...
>  The person familiar with Amazon’s probe casts the sale as a choice to “hack off the diseased limb.”

So this person has lots of details. Again, #12 or #14, but it could be a whole separate person who just focuses on the probe. Also, i may be mistaking the use of 'person' to indicate it's not an insider.

> As for Apple, one of the three senior insiders says that in the summer of 2015, a few weeks after it identified the malicious chips, the company started removing all Supermicro servers from its data centers, a process Apple referred to internally as “going to zero.”

The insiders have usually all corroborated, but this time we get a minority report. Maybe it's not true. Maybe it's happening for other resond.


The remainder of the article discusses trade and has a few more quotes that don't contribute to the technical detail. 

Now, let me deconvolve:
=======================

Source #1

- likely an amazon insider
- knew that amazon did due diligence on elemental
- has no critical information

Source #2

- probably a government official
- knows non-spec parts were found on the board 
- may think the PLA put them there
- might not have knowledge of the apple story

Source #3

- probably an amazon insider
- knows that boards are assembled in china

Source #4

- probably a government official
- thinks the PLA put them there
- knows the investigation started before amazon was involved
- might have no knowledge of the apple story

Source #5

- Government official
- Knows that 30 companies were affected by SOMETHING
- may not have had much other information

Source #6, #7, and #8

- Apple insiders
- mostly corroborate
- All discuss malicious chips - but this could mean BMC firmware issues, Counterfeit, or miscommunication of other issues
- only one claims that they started removing supermicro servers. This could be true for other reasons. This could be false since only one of the three claimed it.

Source #9

- Government officials
- One says there's ongoing investigation to see if spies are planted in supermicro or elsewhere. This is to my best understanding, something that is always happening

Source #10

- Government officials
- One reports that agents think that one of several methods might have been used to convince a factory to add chips. The variety of methods described sounds more like someone explaining possibilities, not someone recounting actual events.

Source #11

- Former official
- makes cliche quotes

Source #12 and #14

- seem to have the most insight.
- one of them know about the white house meeting
- one saw the amazon report, the other saw photos, xrays, and a revised report
- both know how implants work, perhaps from the report
- one is familiar with a government probe, may know details of how it was tracked down to the factory, and that it affected 30 companies.
- one saw a picture of an in-pcb implant in a server in china
- one discussed 'hacking off the diseased limb'

Source #13

- a person
- reports that apple had network and firmware issues attributed to suspicious chips in may 2015

Source #14

- see above

Source #15

- web hosting executive
- got the message to 'get off supermicro'

Source #16 and #17

- probably about the other nontechnical contributions.


So what does it all mean?
=========================


Apple:
------

- Sources #6, #7, and #8 are apple insiders
- Source #13 has one piece of apple information.
- One official said apple didn't give them access to their hardware. Maybe because they weren't affected?

One official said apple was in the list of 30 companies. Four of the 6 officials said apple was a victim
No other apple information is directly attributed to any other source. This appears to be the ONLY link between the two sets of sources.

We don't know for sure what exactly the list is of, an almost any list of 30 tech companies is going to include Apple. I think the link is tenuous enough we can separate them for further analysis. My guess here is that there's some reporting of hardware issues mistaken for hardware implants. There's actual reports of malware in bmc firmware, which can be easily confused for hardware when going through multiple sources and non-hardware people. Apple was lumped into this story, not because anyone found grain-of-rice sized implants, but because they had issues with supermicro that almost lined up.

Amazon - Inconsequential:
----------------
- Sources #1 and #3 are likely amazon insiders. Neither have ant truly relevant information beyond standard amazon business practices (buy companies, do security assessments, build hardware in china)
- Sources #5, #9, and #11 are government officials that provide no technical substance or detail, and only confirm likely obvious facts.
- Source #10 is a government official that appears to give details of how the job was done - but it doesn't read like an account of events, just a theoretical description. Like a journalist asked 'how would the PLA get chips in' and got an honest, if theoretical, answer
- Source #15 is an oddball that is cited very differently from all the others. His tip to 'get off supermicro' doesn't add to technical details of why.
- Sources #16 and #17 were not enumerated.


The Government story:
---------------------

Sources #2 and #4 are possibly government officials and have very similar information

- There was an investigation
- then, amazon found chips
- they think the PLA put them there.

Let's go out on a limb. Amazon did find sketchy chips. They told government officials, who though they might be spy chips. Amazon later analyzed them, and found them to be counterfeits or poorly reworked parts. Amazon's denial is still true, and these sources are still telling the truth. If true - why didn't amazon say this? I don't know, but giving any inch to this story is feeding a conspiracy theory and not going to end well.


Amazon - What Matters:
----------------------
Sources #12 and #14 are the meat of the story. I can tell who said what. There are several things attributed to only one source. The more of those that come from the same source, the worse it is for the integrity of the story. But - we're down to one or two sources for the entire meat of the story. We've got:

- meetings at the whitehouse. But guess what - these happen all the time. The only information about them comes from non-government sources
- amazon reports. Whether or not amazon found spy chips, I'm sure they have their eyes out for them. What happens when amazon says to one official 'you told us to look out for spy chips, we did some research. This is what's possible but we haven't found it in our systems'
- a government probe that identified 30 companies. We still don't know what they identified those companies as. Maybe it's a list of high-dollar supermicro customers?
- a picture of an in-pcb implant in china. My guess is that would be included in a research report.
- complaints about the equipment at the chinese facility - I've never been to china, but i can only guess the PLA has better access to a datacenter in china than one in the USA. They probably even have legally mandated access. Why would you put fancy implants in a datacenter you nearly have the keys to?

So. I started out intending to remap the sources to tell a different story. Instead I feel like I've whittled it down to 1 or 2 reports attributed to amazon that outline some hardware implant techniques. Is this amazon's "project blue book" being used by hardware implant conspiracy theorists, combined with a few confirmation-happy sources and journalists?


I want to Believe:
------------------
One detail still sticks out:

> Gray or off-white in color, they looked more like signal conditioning couplers, another common motherboard component, than microchips, and so they were unlikely to be detectable without specialized equipment. Depending on the board model, the chips varied slightly in size, suggesting that the attackers had supplied different factories with different batches.

This is out of the alleged amazon report. This is why i was asked, 'what's a coupler' and responded with a small signal coupler. It was white and matched the source close enough.

Now with more context, I know what they were looking for. Ethernet cables are magnetically coupled. This prevents high voltage from killing one or another piece of equipment networked together. They used to be discrete components, but now many ethernet jacks have the 'magnetics' built in. On top of that, only a few months ago, there were public claims that Raspberry Pi Ethernet jacks were backdoored with extra components - revealed to be the magnetics and PoE components. What color are these couplers? Usually black, but many times they're grey metallic or white. Also - notice there's no claim of grain-of-rice size here, with the actual description.

All this is confirmed when another story comes out - and ta-da: we've got a purported backdoored ethernet port. We've got claims that metal housings on ethernet ports indicate implants (they don't, they're magnetic shielding). We've also got a source on the record who is light on proof but insists he's got a technology that can detect these malicious implants.

Reconnecting the dots:
----------------------

In 2014, intelligence revealed china's military had plans or capabilities to infiltrate server supply chain. Meetings were held, some companies who might be affected were informed.

Based on that, Apple scrutinized a few hardware issues a little more closely, but found nothing. When they later found malware in a BMC firmware, that was the last straw and they moved on from supermicro.

Amazon was concerned and commissioned or received a report on the risk of hardware implants. They found lots of details on current and upcoming capabilities, but no implants. When they found something fishy with the elemental boards, they were cautious at first, and may have informed government officials, but quickly ruled it out as a typical supply chain issue with counterfeit, low quality, or reworked parts.

Echos of both these stories percolated and details were lost in propagation and translation. The report listing 30 companies was taken out of context. Apple and amazon were lumped together. Someone misinterpreted the amazon report on implant capabilities. Sources confirming small bits of unrelated information were mixed up, and connected improperly. Claims of backdoored ethernet jacks percolated and brought attention to magnetic couplers.

So in the end - nothing really happened that we didn't already know about. But we spent a week pursuing a sensationalist story or three.

