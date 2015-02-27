---
layout: post
title:  "Abstraction"
subtitle: "ATMs, Databases and Justice"
author: "Nick Landolfi"
date: 2015-02-25 3:24:00
categories: lando
---

A few weeks back I wrote a lengthy, pedantic, and extra-ordinarily dense article on interface. It felt right to start from the technical because it was computer science and computer systems architecture that instructed me power in the power abstraction and interfaces. Sadly, I lost the lost sight of the my original goal: to demonstrate how abstraction and interfaces are used in systems design everywhere, and to argue that the better the abstraction the stronger, more resilient, and more useful the system. I attempt to achieve that here.

### How to explain abstraction

"It's like....well...it's kinda like...how. Do you know what a database is?" I finally got out, as my mind was racing with how to explain what it was that so excited me. She stared at me almost condescendingly before she replied: " I mean I've heard of them yes but if you are going to talk about modeling data in elos again I'm not sure I need to know"

"No no no, this is different. Ok, how about ATMS..."

### ATMS

So what does an ATM do? Well, the whole idea is that it's an automated teller machine, that instead of going inside the bank, which is only open so many hours a day, you can get your money outside. That led to banks putting these machines right outside of the building, so you could show up, plug in your card and then get some money.

It was simple enough...I guess, but what if I want to travel to New York, and get money there. It's fine if I can find a Chase, or Bank of America, but if I can't then I'm out of luck...or money. It didn't take banks to long to wonder why they each needed to create their own special ATMs to satisfy customers across the country, or around the world, so slowly the ATM systems arrived, wherein if that ATM catered to your bank you could use it. This makes sense, from a systems design and interface standpoint - I can tell you that now, before even explaining the details. But what want to also point out the pointedly obvious material benefits here as well. Each bank doesn't have to spend resources on building a ATMs all over, they can use use one ATM.

Ok so you go to the ATM and you plug in your information. The ATM that is processing your information doesn't want to know anything about each of the individual banks. All the ATM cares is that the bank for you which you are using has said that your credentials were acceptable. So you deposit a check. Now the ATM sends that information to the bank. The ATM doesn't want to know anything about how the bank is going to store the money represented by that check, it just hands it off the bank. When the bank get's the check, maybe it goes to someone who processes it. Maybe the bank prints the check a verifies signatures. Maybe not. Maybe they verify the check is valid from the bank it recieved. The bank doesn't care how the other bank stores you financial assets. Maybe the bank who's authority backs the check stores your assets in gold. Maybe the bank recieving the check stores assests in platinum. So once they verify the transaction they create a work order for the platinum guy to hand off 2 kilos of platinum to the guy who works the front door of the vault. Who then hands it off to the guy who organizes the saftey deposity box system. And then finally, your platinum get's but in the saftey deposit box labeled with your last name and birth date.

See it doesn't much matter how either bank stores the money (in fact banks don't _really_ store your money, they leverage against debt) because the ATM doesn't care. All the ATM cares about is that the bank knows how to authorize a user's deposit, and that once the ATM tell's the customer they are authorized and accepts the deposit, that the bank can effectively make the deposit. Even the guy verifiying the check doesn't need to know our bank stores assets in platinum. The guy who get the platinum from the main reserve doesn't need to know how the guy who manages the safety deposit box organizes the deposits. No one needs to worry so long as everyone can effectively complete the task they are expected. So long as everyone fulfills their requisite interface.



