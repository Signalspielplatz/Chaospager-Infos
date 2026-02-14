Navigation: [HOME](https://signalspielplatz.de) [HARDWARE](https://signalspielplatz.de/Hardware.html) [BLOG](https://signalspielplatz.de/blog.html) 

# Chaospager FAQ
(For explanations of some basic terminology, go to [Glossary](#glossary))

**Q: What model of pagers are you using?**  
A: We're building our own pagers! Follow this link for more information: [Hardware](https://signalspielplatz.de/Hardware.html)

**Q: What frequency will be used for public broadcasts at 39c3?**  
A: 439.9875 MHz

**Q: Will you distribute your pagers at 39c3? Were/when can I buy a pager?**  
A: We won't be able to hand out / sell any pagers at 39c3, as we're still in the prototyping stage and don't have spare kits availabe. 

**Q: Can I borrow a pager at 39c3 to try it out?**  
A: We probably won't have enough pagers ready until then to hand out loaners; but we're looking for people interestered in testing two prototype versions at our assembly and give feedback.

**Q: Do you have an open repository / info on how to build my own pager?**  
A: At the moment, we are in a heavy development phase. Please bear with us as we are currently unable to provide anything for you to replicate.

**Q: Will the ChaosPager run Meshtastic?**  
A: At least one of our prototype versions is Meshtastic compatible, and it's definitely something we're still keeping in mind for further development!

**Q: I'm new to this, how can I receive your broadcasts?**  
A: You can use any commercial pager (original or modded) as long as it is capable of receiving on 439.9875 MHz and can be programmed to the RICs we use! Alternatively, there are ways to utilize an RTL-SDR for this purpose.

*For compatible pager models, you can refer to this [overview](https://hampager.de/dokuwiki/doku.php#overview_of_paging_receivers).  
❗️Please note that depending on the model, you will need to replace the quartz or at least use a physical interface to program the RIC.
A few members of our group have Alphapoc or modded Skyper pagers for reception tests. While some users have reported successful tests, we cannot guarantee compatibility for all devices.*


# Glossary


**Q: What is a pager?**  
A: A pager is a small, wireless receiver designed to receive short messages over radio. Before smartphones, pagers were widely used by hospitals, emergency services, and nerds of the ’90s to receive alerts quickly and reliably. Unlike phones, pagers don’t send messages back — they simply listen on a specific frequency and display whatever messages are broadcast to their address (called a RIC). They’re simple, robust, and great for experimenting with radio tech today.

**Q: What is DAPNET and POCSAG?**  
A: [DAPNET (Decentralized Amateur Paging Network)](https://en.wikipedia.org/wiki/DAPNET) is a community-driven network used by amateur radio operators to send pager messages worldwide. It relies on [POCSAG](https://en.wikipedia.org/wiki/Radio-paging_code_No._1), a classic digital paging protocol from the 1980s that defines how messages are encoded and transmitted over the air.   
In short: POCSAG is the radio protocol, and DAPNET is the modern network that uses it to deliver messages to pagers.


**Q: What is a RIC?**  
A: A RIC (Radio Identity Code) is a pager’s address represented as a fixed-length bit sequence in the POCSAG protocol. Each transmitted message includes this address, and the pager scans the incoming bitstream, only accepting frames where the address bits match its programmed RIC. This bit-level filtering lets many pagers share one frequency without mixing up messages.   
Multiple pagers can programmed to the same RIC, and one pager can be programmed to receive more than one RIC. Therefore, a group of pagers can be alerted at once — which is our goal for the cooperation with CERT — and each pager can "subscribe" to multiple topics.

**Q: Who/what is DL0TUH?**  
A: [DL0TUH](https://de.wikipedia.org/wiki/DL0TUH) is the amateur radio group at the Hamburg University of Technology. We are collaborating with them to realize our project.
