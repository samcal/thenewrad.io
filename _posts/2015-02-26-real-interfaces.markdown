---
layout: post
title:  "Abstraction Dialogues"
subtitle: "ATMs, Databases and Justice"
author: "Nick Landolfi"
date: 2015-02-25 3:24:00
categories: lando
---

A few weeks back I wrote a lengthy and extra-ordinarily dense article on interfaces. My inclination to adopt a strictly technical perspective on interfaces was rooted in the history of my own understanding of abstraction through the lens of computer systems. Sadly, I lost sight of my original goal of demonstrating the role abstraction and interfaces play in systems design everywhere. I also failed to demonstrate that better abstraction leads to stronger, more resilient, and more useful the systems. I attempt to accomplish these goals again here.

### Explaining abstraction

>"It's like....well...it's kinda like...how. Do you know what a database is?"

I finally blurted. My mind raced... I searched for how to explain what it was that so excited me.

She stared at me, there seemed a slight condescention in her reply:

> "I mean I've heard of them yes but if you are going to talk about modeling data in elos again I'm not sure I need to know"

> "No no no, this is different. Ok, how about ATMs..."

### What does an ATM do?

Well, the whole idea is that it's an automated teller machine, that instead of going inside the bank, which is only open so many hours a day, you can withdraw your money outside. That resulted in banks installing these machines on the exterior of their building. You could show up, plug in your card and then get some money.

It was simple enough...I guess, but what if I travel to New York, and want to withdraw some money there. I'm perfectly well off if I can find a Chase, or Bank of America or whichever bank of which I am a patron. If I can not, however, find my bank, then I am out of luck...or money.or money.

She laughed.

Banks soon began to wonder at why they each needed to a vaste network of their own special ATMs to satisfy customers across the country, or around the world. So slowly the ATM infrastructure services arrived. If an ATM "type" catered to your bank, you could use it. Ahh let us admire the specialization economy. The ATM service can provide the best ATM experience for consumers, while allowing banks to expand their ATM premise at a fraction of the price it would cost to install their own specialized machines.

She was nodding...good!

This makes sense, from a systems design and interface standpoint - I can tell you that now, before even explaining the details. But what want to also point out the pointedly obvious material benefits here as well. Each bank doesn't have to spend resources on building a ATMs all over, they can use use one ATM.

"Mhmm, " she agreed.

Ok so you go to the ATM and you plug in your information. The ATM system that is processing your information need not know the specifics of your personal bank. The ATM only cares that your bank can authorize your credentials. This is the first example of an interface (commonly known as an API). The ATM asks the bank's system to do the authentication - the ATM itself does not have all of the banks records on store to check.

> "ok..."

*I got the impression I should speed up my explanation.*

So you deposit a check. Now the ATM sends that information to the bank. Similarly to the authentication, the ATM doesn't want to know anything about how the bank is going to store the money represented by that check.

> "Right"

It just hands it off the bank! When the bank recieves the check, maybe it goes to someone who processes it. Maybe the bank prints the check and verifies signatures. Maybe not. Maybe they verify the check represents valid credit.

> "Oh, and the bank doesn't care how the other bank stores resources so long as it can say the credit is valid?"

Exactly! It doesn't matter how the other bank stores the financial assets - just that they do. Maybe the other bank backs the check in gold, or cash, or bonds...doesn't really matter. In fact currency is itself an abstraction!

> "Right right, because you don't have to _really_ know what it represents.

Yes, yes.

> "Anyway, back to our bank."

Right, maybe our bank - the one recieving the check - stores assests in platinum. So once the the transaction guy verifies the deposit he creates a work order for the platinum guy to hand off 2 kilos of platinum to the vault guy who guards the front door of the vault. The vault guy then hands your two kilos of platinum off to the guy who organizes the saftey deposity box system. Finally, he is the one who puts your platinum in saftey deposit box labeled with your last name and birth date.


It doesn't much matter how either bank stores the money [^1] because the ATM doesn't care. The ATM cares only cares that the bank knows how to authorize a user's deposit, and that once the ATM tell's the customer they are authorized and accepts the deposit, that the bank can effectively make the deposit. Even the guy verifiying the check doesn't need to know our bank stores assets in platinum. The guy who get the platinum from the main reserve doesn't need to know how the guy who manages the safety deposit box organizes the deposits. No one needs to worry so long as everyone can effectively complete the task they are expected [^2]. So long as everyone fulfills their requisite interface. The bank, in this scenario, is an abstraction of the essential functions of a financial institution. We have a word for this collection of functions: it is, in fact, called a bank!

> "Hahahaha, Ok ok how is this at all like datbases?"

Ahh! You see, it's exactly the same. Instead of money, databases just store data. The interface for database is basically anything that can save and find itemized pieces of data. There are a ton of ways to store the data, but it doesn't matter how the functionality is implemented. The most effective way to design any system that uses a database is such that I don't depend on any particular implementation. The ATM wouldn't be much use if it always required the crediting bank stored assets in gold and the receiving bank storesd assets in platuninum. Our ATM didn't worry about any bank in particular, just a bank that could authorize a user and recieve a deposit. So today elos uses one database, but we are not bound to it. If there is, as there almost certainly will be, a better database in the future, elos can just drop it in and it will work:elos is built around the idea of a database. There could be crazy implementations. My favorite example is that elos could use an implementation that sent data to a chimpanzee keeping track of bits on a whiteboard. So long as that chimpazee could store and retrieve (and maybe query) data, it would work (though would be slow af).

> "Ok so when you 'code,' when you build your elos system thing, you don't think about the database"

Right! That's abstraction.

> "Wait, and interfaces are..."

The contract that I have with that abstraction. Saving and retrieving records is the interface of the database. Authorizing and depositing that of the bank. But a database and  a bank are both abstractions.

> "Hmm, cool....ok. Well I guess... I mean you said this applied to all systems, but what other..."

I'm glad you asked! I contend that abstraction and interfaces are so effective that we have arrived there in our justice system as well.

*Confused look*

No no, hear me out.

 I think justice has evolved over time. Aristotle talked about the good life, the one right way to live. Then Kant talks instead about the treating humans as ends in themselves - no suggestion at how to live per say, but a suggestion on how to act (this is the part of Kant’s philosophy I do like). Finally Rawls appears and says there is no one right action or course of life, you need only satisfy certain requirements: namely treat people with respect. I think we have evolved from the difficult over-reaching perspective of prescriptive morality to a more abstracted notion governing morality. After all if you want to generalize something to work over all situations you have to generalize somewhat. So long as you act in a way not at odds with these certain principles, you are ok.

 This is what the Declaration of Independence did to human rights. “Life, liberty and the pursuit of happiness.” The role of the government is to protect these rights, and each human is afforded these inalienable rights by nature of living. There’s no right way to govern, but any government must not infringe upon these inherent rights. Maybe Kant shouldn’t be saying there is exactly a correct morality, but rather so long as you treat people as an ends in themselves (rather than a means to an end) you are generally ok. I prefer that perspective.


[^1]: Banks don't _really_ store your money, they leverage against debt.
[^2]: There is a level of trust present here
