---
layout: post
title: "Unihack Sydney 2018"
date: 2018-08-23
image: "/assets/img/blockMed.jpg"
credit: "Gerard Hosier"
categories: blog hackathon blockchain
---

Over the weekend of 4 - 5 August 2018, I attended Unihack Sydney. This was the first hackathon I'd ever been to so it was a pretty new experience for me.
I arrived on the morning of Saturday the 4th with a few ideas to work on - but with no team to work on them with. So I formed a team with 6 others who had no team and we began a brainstorming process to find a problem that we considered worthwhile and interesting to work on.
There were two main ideas that were narrowed in on that the team liked; the first being a series of games to help assist recruiters find good applicants while minimising personal bias. The other was a blockchain application that would replace paper prescriptions to enhance the security over paper prescriptions, and to reduce the centralised nature of existing digital prescription services available in Australia.
In the end, we split the team of seven up into two smaller teams; partly because people wanted to work on different things, but also because it became quickly apparent that without planning before the event it would be difficult to find roles for each team member.
I ended up working on the blockchain prescription system - which we called BlockMed, with two others (plus another who didn't show up on the second day).

## BlockMed

### The elevator pitch

BlockMed takes prescriptions and puts them on the blockchain. This ensures that prescriptions cannot be cloned, and are immutable. It also has advantages over existing digital prescriptions in that it removes the centralisation which is unavoidable in a traditional digital solution.

### Our reasoning for chosing this project

We chose do work on BlockMed for two main reasons:
 1. None of the members in the team had much experience with blockchain (except for me who had a little), and wanted to use it as a learning opportunity to 
 2. It seems like a good aplication for blockchain; being able to assign a prescription to a specific person with no chance of it being modified or cloned.

### Our solution

Given the time constrains - especially given that our team was comprised of members who had never met before Unihack, it was difficult to create a complete solution. Therefore, we had created a prototype of the backend - ie the smart contract - written in solidity that was published on the Ethereum test network (Ropsten).
It is currently published on the test network at [0x6e6DB4F6358360872AdA68EeA2c61FCaF9d1Eed5](https://ropsten.etherscan.io/address/0x6e6db4f6358360872ada68eea2c61fcaf9d1eed5), and the source code can be found on [github](https://github.com/bowdens/blockmed).

In the current state, the prototype has an administrator, which is the ethereum address who published the smart contract. They are responsible in this protoype for maintaining the list of addresses associated with doctors and pharmacies. This is not an ideal solution, but being a prototype, it was the easiest to implement.
Any address which is added as a doctor by the administrator has the ability to create a Prescription, which in our protoype is represented by a drug name, a quantity, a patient name, and a patient delivery address. These prescriptions can be marked as fulilled by any address which has been marked as a pharmacy by the administrator.

### Advantages of the solution
* As it exists in the prototype form, our solution has some advantages over traditional paper prescriptions. It is impossible, in our system, for anybody other than doctors to create prescriptions.
* Once fulfilled, it is impossible for a prescription to be redeemed twice.
* It is also impossible to modify a prescription once created.

### Disadvantages of the solution
* The most glaring disadvantage for this is the ease of use. It is currently relatively difficult for end users to interact with the blockchain. The best method is using a browser plug in like metamask, but that requires remembering an additional password, and backing up a seed phrase.
* This solution would also require doctors to pay the miner fee each time they want to create a prescription - usually somewhere between 10 cents and $1. This means doctors and pharmacists would have to keep a supply of ether on hand, also meaning they need to register for an exchange or similar.
* Another potentially huge problem is that of private key storage. If a bad actor gets their hands on a doctors private key through whatever means (phishing, social engineering, etc) then they can create as many prescriptions as they want, which in the eyes of the blockchain are 100% valid.
* The system does not prevent any problems like corruptible doctors or pharmacists, or validation that the drugs recieved are the drugs that were prescribed.
* In the current prototype there are big privacy issues. Because all transactions on the Ethereum blockchain are public, all prescriptions created are public too, meaning anybody who cares to look can see a patients name, the drugs they are recieving, and their address. We discussed several ways to solve this, but did not implement it in the prototype. These included:
 * Hashing + salting the data so that it is either the customers or a traditional servers responsibility to know what the original data was and using the blockchain to verify the data only - this would also cut down on the costs of creating prescriptions because the hashes are smaller than arbitrary length strings.
 * Encrypting the data before putting it on the blockchain. But in this case, it seems that you might as well just use traditional cryptographic methods and bypass using the blockchain.


## What did I learn?

### About blockchain
* Blockchain, from an end users perspective, isn't there yet. Users don't want to pay fees for basic services like creating or fulfilling a prescription. Users also have to worry about their private keys and owning ether (or which ever currency is neccessary). Ideally, blockchain might get to the point in the future where users don't need to know or care about it - like HTTP or the DNS system works currently. Few internet users know or care about how HTTP or DNS works yet it is instrumental to the internet and works seamlessly in the background every time they visit a website.
* It's really hard to get smart contracts right. And if a single detail is wrong, a security hole could be created and exploited, and smart contracts cannot be patched.
* Blockchain isn't the ideal solution in many cases. It seems that the existing digital prescription solutions are far more practical than any blockchain solution is, at least for the forseable future.

### About Hackathons
* It's probably a good idea to organise your team and idea before the hackathon - It was a fun challenge to meet new people and discover their interests and strengths and create a project around that, but if you want to be competitive, you should have probably come up with an idea beforehand and be familiar with your team.
* Sometimes the simple ideas are better than the high minded abstract ideas. It's all well and good to say that you want to create a system to revolutionise medical prescriptions, but nailing down exactly what that is and coming up with a good solution with a front end and back end is more difficult.
* Hackathons are pretty awesome and you get to meet a whole bunch of likeminded people. I look foward to going to more in the future.


