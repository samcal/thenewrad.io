---
layout: post
title:  "Abstraction Dialogues"
subtitle: "ATMs, Databases and Justice"
author: "Nick Landolfi"
date: 2015-02-25 3:24:00
categories: lando
---

A few weeks back I wrote a lengthy and extra-ordinarily dense article on interfaces. My inclination to start from the technical side of interfaces was rooted in my own understanding of interfaces and abstraction through computer systems. Sadly, I lost sight of my original goal of demonstrating the role abstraction and interfaces play in systems design everywhere. I also wanted to argue that the better the abstraction the stronger, more resilient, and more useful the system. I attempt these goals again here.

### Explaining abstraction

"It's like....well...it's kinda like...how. Do you know what a database is?" I finally got blurted, as my mind was racing with how to explain what it was that so excited me.

She stared at me almost condescendingly before she replied:

"I mean I've heard of them yes but if you are going to talk about modeling data in elos again I'm not sure I need to know"

"No no no, this is different. Ok, how about ATMs..."

### ATMs

What does an ATM do? Well, the whole idea is that it's an automated teller machine, that instead of going inside the bank, which is only open so many hours a day, you can get your money outside. That led to banks putting these machines right outside of the building, so you could show up, plug in your card and then get some money.

It was simple enough...I guess, but what if I want to travel to New York, and get money there. It's fine if I can find a Chase, or Bank of America, but if I can't then I'm out of luck...or money. It didn't take banks long to wonder why they needed to each create their own special ATMs to satisfy customers across the country, or around the world, so slowly the ATM infrastructure services arrived, wherein if a particulary kind of ATM catered to your bank, you could use it. This itself is an example of the power of a specialization economy. The ATM service can provide the best ATM experience for consumers, while allowing banks to expand their ATM premise at a fraction of the price it would cost to install their own specialized machines.

She was nodding...good!

This makes sense, from a systems design and interface standpoint - I can tell you that now, before even explaining the details. But what want to also point out the pointedly obvious material benefits here as well. Each bank doesn't have to spend resources on building a ATMs all over, they can use use one ATM.

"Mhmm, " she agreed.

Ok so you go to the ATM and you plug in your information. The ATM system that is processing your information doesn't want to know anything too specific about your individual bak. The ATM only cares that your bank has authorized your credentials. This is the first example of an interface (commonly known as an API). The ATM asks the bank's system to do the authentication - the ATM itself does not have all of the banks records on store to check.

"ok..." I got the impression I should speed up my explanation.

So you deposit a check. Now the ATM sends that information to the bank. Similarly to the authentication, the ATM doesn't want to know anything about how the bank is going to store the money represented by that check.

"Right"


It just hands it off the bank! When the bank recieves the check, maybe it goes to someone who processes it. Maybe the bank prints the check and verifies signatures. Maybe not. Maybe they verify the check represents valid credit.

"Oh, and the bank doesn't care how the other bank stores say the credit is valid?"

Exactly! It doesn't matter how the other bank stores the financial assets - just that they do. Maybe the other bank backs the check in gold, or cash, or bonds...doesn't really matter (note: currency is, in a sense, an abstraction).

"Right right, because you don't have to _really_ know what it represents.

Yes, yes.

"Anyway, back to our bank."

Maybe our bank - the one ecieving the check - stores assests in platinum. So once the transaction verification guy verifies the transaction he create a work order for the platinum guy to hand off 2 kilos of platinum to the vault guy who guards the front door of the vault. Who then hands it off to the guy who organizes the saftey deposity box system. And then finally, your platinum gets put in a saftey deposit box labeled with your last name and birth date.


See it doesn't much matter how either bank stores the money (in fact banks don't _really_ store your money, they leverage against debt) because the ATM doesn't care. All the ATM cares about is that the bank knows how to authorize a user's deposit, and that once the ATM tell's the customer they are authorized and accepts the deposit, that the bank can effectively make the deposit. Even the guy verifiying the check doesn't need to know our bank stores assets in platinum. The guy who get the platinum from the main reserve doesn't need to know how the guy who manages the safety deposit box organizes the deposits. No one needs to worry so long as everyone can effectively complete the task they are expected. So long as everyone fulfills their requisite interface. The bank, in this scenario, is an abstraction of the essential functions of a financial institution. We have a word for this collection of functions: it is, in fact, called a bank!

"Hahahaha, Ok ok how is this at all like datbases?"

Ahh! You see, it's exactly the same. Instead of money, databases just store data. The interface for database is basically anything that can Save and Find itemized pieces of data. There are a ton of ways to store the data, it doesn't matter how the functionality is implemented though, and the best way to design my system is such that I don't depend on any particular implementation. Much like the ATM didn't worry about any bank in particular, just a bank that could authorize a user and recieve a deposit. So today elos uses this one database, but we are not bound to it. If, as there almost certainly will be, a better database in the future, elos can just drop it in and it will work. Because elos is build around the idea of a database. Not of a particular store. My favority example is that elos could just a database that sent data to a chimpanzee keeping track of bits on a whiteboard. So long as that chimpazee could store and retrieve (and maybe query) data, it would work (though would be slow af).

"Ok so when you 'code,' when you build your elos system thing, you don't think about the database"

Right! That's abstraction.

"Wait an interfaces are..."

The contract that I have with that abstraction. Saving and Retrieving is the interface of the database. Authorizing and depositing that of the bank. But a database and  a bank are both abstractions.

"Hmm, cool....ok. Well I guess, I mean you said this applied to all systems, but what other..."

I'm glad you asked. I contend that abstraction and interfaces are so effective that we have arrived there in our justice system as well.

*Confused look*

No no, hear me out.
