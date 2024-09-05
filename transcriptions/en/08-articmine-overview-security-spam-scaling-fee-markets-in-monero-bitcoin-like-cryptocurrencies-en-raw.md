# ArticMine

_**Overview Security, Spam, Scaling & Fee Markets in Monero & Bitcoin Like Cryptocurrencies**_

[https://youtu.be/KuIRDTsyzkQ](https://youtu.be/KuIRDTsyzkQ)

---

_**Francisco:**_ My name is Francisco Cabañas, also called ArticMine. And we're going to cover some of the questions of security, spam, scaling and fee markets in Monero and Bitcoin like cryptocurrencies.

Now I'm going to have some definitions here. I'll briefly go through it. TR being the reference transaction size, MB being the block size in bytes. I'm introducing a concept called the block period in seconds, which is basically how many seconds are between blocks. And the range of about 120, two minutes in Monero, 10 minutes in Bitcoin and Bitcoin Cash. Some coins are faster. Zcash is to 75, Litecoin is about 150. One that is really fast is Ethereum, and then like 12 to 15 seconds between blocks. So, RBase is the block reward. F is the total fees in block.

Then you may have a miner penalty and minor costs. Now, minor costs, we don't usually talk to them about, but there is some literature on the subject. And what it means is that a miner would incur costs due, for example, to open blocks. One article, it was from 2015, Peter Rizum had a theory on this. And you actually get a second penalty term added to the end of basically based on the probability of open blocks. The main thing that I found about this is that it also is proportional to the block reward. But so you can have, you can build in a market cost for the miner. In Monero, of course, the big M is the penalty and the penalty calculations.

The next one is what I call the maximum block size at time in mining. This is basically how big a miner at a point in time can grow the block size. Does not mean what it can grow down the road. Of course, in some clients it's fixed. In others it's not. So in Monero, for example, it's like twice the median for the penalty calculation at any point in time. So that's how big they can grow it. In other coins, it's just completely flat, a static number, and it cannot be changed.

And then, of course, the percentage increase in the block size, which is B. This is a parameter that we use in Monero a lot. And what that tells you is, if I, for example, have a block of 300,000 bytes, or I increase it to 3 million bytes, that's like a tenfold increase. We wouldn't be able to do that, but for 300,000 bytes, let's say I do a 10%, which would be 30,000 bytes, then that would be then the increase. So that's 0.1. And if you do like a 1% or 0.01, so that just tells you the percentage increase that you do. The most you can have is B equal 1 and Monero. And of course, that's the requirement of the Monero protocol.

So let's look at what a fee market is in a proof-of-work cryptocurrency. And we all talk about fee markets, but what are they really? So a fee market is the free commercial interaction between miners and users of a cryptocurrency, where both the miners and the users act in their enlightened self-interest. So what you have is a free market between the miners and the users. They act in enlightened self-interest, and they come up with a price and the prices for a transaction transfer, for actually sending a transaction. The rules for the fee market are defined in the consensus protocol of the cryptocurrency. So when we talk about fee markets, we're really talking about what set of rules did the cryptocurrency create that led to that fee free market. So it's defined ahead of time. And it's defined in the design of the cryptocurrency. Because a lot of people think of fee markets are going in certain coins, but in other coins, I would say that we see an example. There's a fee market. The question is what shape it takes.

Okay, so it's types of fee markets. So how can you set this maximum block size? Well, you can do a whole bunch of things. You can do it in a consensus protocol. Very famous case being Bitcoin. They set it at one megabyte. And then they thought about it for well over a decade now. And then they decided: well, we're only gonna count a portion of the transaction I "SegWit" and effectively increase the block size. So this is a consensus protocol set, and it can be very, very difficult to change.

Another method that, for example, it was quite prevalent in Ethereum, is miner voting. And you have situations where the miners would indicate how big a block size they want, typically by what they put in the attack placed in, for example, in the block hash, in the block itself. And then they mine on what, they vote effectively on what the block size would be. In the case of Ethereum, that would be the gas limit. And then you also get a political controversy, and you can read the history in the Ethereum community on this, of changing the gas limit because the fees are too high and the gas price is too high. By the way, gas in Ethereum can be roughly thought of as the block size. What it is designed to do is the Ethereum is very much a processing cryptocurrency that does actual processing as opposed to just storage of data, which is the focus of, for example, Bitcoin and Monero in the cost.

So then you have medium driven adaptive block sizes with or without a penalty. One case was proposed by BitPay and Bitcoin, I believe around 2016, and they had a median of some over 2000 Bitcoin blocks. And then they used the median in this proposal to adjust the block size. That sounds a lot like Monero, but without one thing - the penalty.

When we're looking at penalty-driven block sizes, Monero is, of course, the biggest with this kind of approach - originally came from CryptoNote - and the concept is that you forfeit a portion of your block reward in order to increase the block size above the median. This is the kind of concept that Monero uses to scale. Now, you're forfeiting something, which is your block reward, so it's intimately related to that block reward, your securities. It's something you keep in mind. If you say: well, we're not going to have a block reward, we're just going to have a penalty but no cost to it, it doesn't expose the problem.

So there are two scenarios. There's no penalty, neither penalty, nor other miner cost to reach the MBMax, i.e., your largest box size, or there's a penalty or other miner cost to get there. And that's an example of two scenarios of fee markets.

So we look at the rational miner. The rational miner, rational users act in their enlightened self interest in a free fee market, they're not altruistic, and they're not malicious. A rational miner wishes maximum returns, while also dealing with rational users who want to pay the lowest fee that will get their transaction mined.

So we have an interesting problem here. The problem actually is a bit simpler, a bit more complicated in the first look. Given the finite number of transactions in the transaction pool, with the distribution of weights and fees. Now I'm using weights in a generalized sense, for example, would be Bitcoin with SegWit, you use a weight as opposed to an actual size in order to get this portion that is going to be counted towards one megabit. And Monero uses it in certain transactions the other way around to account for the verification cost of Bulletproofs for a very large number of outputs, more than 2, like 4, 8, 16. And so you have this extra parameter that you actually use rather than the strict block size.

And then the question is: how do you maximize the return to the miner and minimize the cost to the user? And it's actually what's called a discrete optimization problem, and you can solve it exactly. But in a practical sense, this type of problem can take longer and be not worthwhile. It can be approximated. It can be simplified. But there is actually, and the reason you have a discrete optimization problem is because you have different sizes of transactions and you want to optimize the best fit in the box kind of situation.

So let's look at that simple case of fee market with no penalty and no miner cost. So what we do is we make an approximation to the discrete optimization problem. And I call it the "infinitesimal transaction approximation". And what we say is the size of each transaction is much smaller than the block size or the portion of the block size that you're trying to increase. And so what the miner does is the miner orders the transactions in the order of fee paid per byte. The miner then adds transactions to the block, starting with the highest paying transactions first. And then the certain criteria for the miner to stop. Miner runs out of transactions, or the miner runs out of space in the block, i.e., MBMax is reached.

So there's two situations here. One can think of the first example as the big block Bitcoin model. Bitcoin Cash, SV, but also a lot of coins such as Litecoin, Dash, FIT, Profile, Dogecoin. Essentially, they have a fixed block size and they're not filling it up all the time. Theoretically, and in fact, this was the case for Bitcoin in its early years - you don't have any fees at all. And in fact, if you were trading, dealing with Bitcoin in 2011, 2012, 2010, even 2013, past 2014, you could transaction in the Bitcoin blockchain with no fees at all. Which is essentially the big block scenario. And the other scenario, very famously discussed in Bitcoin, but also some degrees in Ethereum is where you have this maximum block size reached. And then what you have is essentially a supply and demand problem where no matter how much you increase the price, you do not increase the supply. Which is why you get these very high fees in Bitcoin and also in Ethereum. So you have a fixed block size. And the only thing you can do if you want to get it is pay a higher and higher price. But no matter how high a price is paid, and this is really important - you do not increase the supply.

Typically markets don't work like that. Increasing the price either increases the supply or what I suggest can also happen if you have a situation like that, is that they look for something else instead. And a very famous example, in 2017, the transaction rate of Litecoin went up 80 fold. Why? Because the Bitcoin blockchain reaches limit. People needed, for example, Bitcoin to go to another coin or another token, say from fiat, Bitcoin to something else, and they picked Litecoin to do the job. And so we had a sudden surge in the demand for transactions on the Litecoin blockchain. Subsequently thereafter, Bitcoin Cash came online, it took some of the pressure off. And then you see more and more SegWit in Bitcoin that also took a lot of the pressure off. So while Litecoin had a huge rise in transactions in 2017, it kind of leveled off since then. But it does illustrate this problem that what you have in a situation where a fee market like Bitcoin is essentially a fee market where no matter how much you increase the price, you do not increase the supply.

Okay, so now we're going to do something else. Now we're going to add a penalty on miner cost. So again, the same approximation, discrete approximation. We'll do the same thing again. The miners orders the transaction in order of fee paid by byte. Same idea. The miner adds transaction to the block starting with the highest paying transaction first. Correct. However, there's one more thing the miner has to do. The miner tests each transaction for profit against the penalty and or the miner cost of both, whatever applies. The miner stops when the miner runs out of profitable transactions, or again, the miner runs out of space in the block, and MBMax is reached.

Now, what's really interesting about this type of model is how this impacts the fee market. Because what we see is the miner has ordered the transactions, and this is very important, and order the highest transactions first. So if you have an example where, so they're gonna get mined, and then the lowest paying transaction matches what it costs to add it, is the one that stops. So the highest penalty or cost is paid by the lowest paying transaction in the block. And after that, it's not cost effective to the miner. A common misconception you can make in this situation is simply say: well, I've got X amount of penalty, and I need X amount of transactions, I can fit them all. No, because the miner is going to optimize. And what the miner is going to do is put in the highest paying transactions first. And then it's only the lowest transaction that pays the marginal penalty. So this is a very important point because it comes into the next slide, which is the Monero fee market.

So Monero actually uses long-term median, ML equals 100,000 blocks, and a short-term medium, MS, of 100 blocks. These are two-minute, 120-second blocks. ML is a medium of a block. And the formula is a recursive calculation. MB is your block size. And then you have 1.7 ML, ZM is your penalty-free zone in Monero. Come to that point later. And then you're looking at the ML/1.7. So this is basically, so you're looking at the minimum of the block size and 1.7 ML. So it's self-capping. And then you maximize the higher off your minimum block size, ZM, and your base, which is the reciprocal ML/1.7. So it provides stability. And it's a recursive calculation.

Now, in my analysis here, and this is a change, sort of a last minute change I made. There is a really interesting question. What is ZM and how is it set? So ZM is set up at existing, currently right now, at 300,000 bytes. For a transaction, a reference transaction size of 3,000 bytes. So we're looking at 1%. And that is a parameter that is set to get things started. It's designed to set the fee in a reasonable point. If, for example, as was mentioned in an extremely interesting talk earlier this morning, you want to increase the typical transaction size in Monero to 10,000 bytes, then you have to change this parameter, which is your penalty-free zone, to a million bytes. So you keep the same ratio. If you don't, you can run into serious problems because what will happen is fees will skyrocket. In fact, they will skyrocket roughly by about tenfold. And you'll also have problems with the approximation, which I was referring to, of the infinitesimal transactions, because now your transactions would be, for example, about 3% rather than 1% of your penalty-free zone. So in Monero, what happens is you have a penalty-free zone, which is your first 300,000 bytes. You don't pay a penalty. And then when you go above that, you start paying the penalty. So this is the parameter that you change in this example. But it's a simple change.

So now we have the medium and extra-longitude. So this is the MS, the short-term medium. I'm going to point out a couple of things, and they're important. So it's the maximum of MB, ML. So ML is your dynamic penalty-free zone. It has to be above the base amount of 300,000 bytes. So you maximize that and you're blocked. So it's the amount above that. It's the minimum of those two you have the minimum of 50ML. And what that is, is a surge factor.

Now the surge factor is how much you allow the short-term medium to rise above the long-term medium. And why would you want that and what is the rationale? Originally, it was said to allow for some scaling without moving the long-term medium. But one of the main reasons for it is an understanding of how credit card transactions work and in particular, the Visa network.

And there's a certain time of the year in Europe and North America being December 23rd, when there is a peak in the total transaction activity on the Visa network. And it's roughly a factor of 16. And that's the holiday shopping. There are a couple of other holidays that could trigger it, and they have a different cycle. Chinese New Year is one of them. Also, the Islamic holidays, and they're on a lunar calendar, they could trigger a surge in economic activity, significant enough. And then you can think of sort of scenarios where you kind of put them one on top of each other and maximize the probability that Eid and Christmas kind of fall at the same time and thereby you have a bigger peak than you normally have.

But the thing important about designing a payment network is that you've got to have this capability to scale upwards in a very short period of time to accommodate this demand. And there's a lot of history on Visa on them. They typically run their network, but it has average transaction rate, because they know that these three or two or three days of the year or one day of the year they're gonna hit 16 times or 17 times and so they have to account for this one day of the year. And we have to do the same thing if we're gonna be serious about being involved in payments, I am not aware any other cryptocurrency that does this, but when people talk about block sizes, a very interesting rule of thumb is you would need the transaction capacity of Bitcoin, and then a factor of 16 is the transaction capacity of Bitcoin Cash in order to address this dynamic of the surge in a holiday. I can say they're maximizing controversy for people in the Bitcoin community, but the fact of the matter is the with SegWit would roughly about a 16 factor difference between Bitcoin and Bitcoin Cash. And that is the kind of surge factor they actually need. 50 is likely on the high side, and this is something that can be tightened.

So now we look at the various cases that we have. Well, you have a penalty Rbase(B+BT)2. So essentially what you're doing is you're taking the block reward and you multiply by the increase in the block size. You square that. And that's basically what your penalty is. In a case one, we get the short-term medium is greater than long term medium. And then you're in the penalty zone. And your transaction size is less than this 50ML. So you're not into hitting that other barrier. And I call this a pure Monero case.

And then you add a transaction check T at a point B in the penalty and define B, BT, MS - this is actually the incremental increase in the penalty. And you get a formula, which is the difference between the old and the new penalty, is that our base, that's your base reward, to be B is the point at which in the penalty you're at. So for example, it could be 10% or 2%. And BT is the additional penalty, so the additional increase in block size by that transaction you added. So what you're looking at is the additional penalty that you pay to add a transaction. And this is a very important formula because what it tells you is, this is what the miner's gonna ask in fees to include that transaction in the block. So the miner's gonna want at least to cover the penalty in order to include the transaction. And this is the formula that effectively determines fees in Monero. It's a subtle thing, but essentially you're looking at that increase in penalty from adding a transaction to a block. So what you want is a fee has to be bigger than this to overcome the penalty.

Okay, so then we have a different case. Case two is MS is bigger than ML, and MB is greater than 50 ML. Now, this is a very unique case, because in this case, what you have is your short-term median is maxed out. You could not increase the short-term median anymore, but you still get one more doubling of the block size. So you have a situation where you have to pay the maximum penalty to Monero, and then it's the one case in Monero where you have a Bitcoin-like behavior. You have all the transactions competing against each other for that shrinking block space. So this high-end case, you basically have your pay Monero fees plus Bitcoin fees. So this becomes it.

So this case, again, you have to not only overcome the penalty, but also to compete Bitcoin style with other transactions against the fixed MBMax, since MS can no longer scale. So you have both of them together. And so it's actually a sort of a very expensive barrier. So rather than having a hard limit when you hit the long-term median, you can best think of it as a very stiff spring that gets stiffer as you press it. So more like a railway spring, for example. It absorbs the energy. So you start very slowly and it stops the train without smashing what's behind it. And what Monero does is it kind of cushions its way in at the level. It doesn't just hit a stiff barrier. So it's a stiff spring.

So now we have the next example, which is called the large block Bitcoin case. Now in this case, there's no penalty. So your FT is zero and your BT goes zero. Theoretically, the fee is going to be zero. This is in fact the case with Bitcoin or Bitcoin Cash, because it was the same coin at that point in time, until about 2014-2016, where there was still room in the blocks you would expect the total fees per block to be lower than in Monero. There's no friction. So if you think about the fee market, most of the transactions are zero. In Monero, you have a penalty. You're going to expect to pay less in fees. And in fact, Bitcoin Cash fees right now are lower than Monero fees, which kind of justifies what I'm saying.

The reason Monero can support a minimum fee, because that's actually the point we're in right now, is because it's a threat of the penalty. So right now in Monero, we're setting about half the block size to get into the penalty zone. So there's the possibility that we'll go into the penalty. In fact, it happened just before the last hard fork that we went into the penalty. So you have to have this minimum fee, which will support the future penalty. And this is, again, important. It's a threat of the penalty. This fee in the past, when we were further away, it was considerably less. It was like 20% of the penalty fee. So we had a very low node relay fee, simply because we were far away. But again, that's the thing. One of the problems that you see in these large Bitcoin cases is the risk of a spam attack when MB, i.e. a block size, are very much less than the maximum block size.

A great example of this was the recent attack on Zcash, where exactly that situation occurred. Now what Zcash did is they said: "Well, we'll take Bitcoin, we have to have transactions that are roughly eight times the size, so we're going to simply increase the block frequency by eight times, and kind of copy everything over. Oh, and then we'll have privacy to boot." Because one of the reasons Bitcoin can get away with having free transactions is because of the fact that the transactions were sort of looking similar to each other. Now they're not looking similar. So Zcash got attacked with a very large Z-transaction, which is the private transactions in Zcash, address half the block. They said they didn't do that pricing right. And they had a very, in fact, it was a very, very cheap attack. And this spam went on for like months. So about August of last year, right into the fall of last year. And it was like they were headphones. And you're going to watch these blocks with a single transaction, a single said transaction, basically taking half the block. Very easy to attack.

So when you don't have proper pricing, spam becomes a real risk. The next thing is if you have privacy, spam becomes an even greater risk, because you can't use censorship as an anti-spam measure. That's how we deal with a lot of spam on email. We censor it. We don't like the word, but that's what we do. This server produces spam - we will block it. This would do an analysis of transactions to see if it's spamming, and we'll basically dump it. I have spam filter, which essentially looks at the dynamics of transactions. I have a spam folder on my Linux box full of Windows viruses that I've trained over the years to treat a spam. So I have a massive collection of Windows viruses in my Linux inbox. Spam volume, because that's what I trained the filter to do. It's getting interesting. But censorship is not an option. So the only way you can deal with spam when you have privacy is by pricing.

Now, a good example is the Big Bang attack. The Big Bang attack was proposed - basically, you just throw a lot of transactions to it. And your cost pay, again, goes as for the going to the penalty. So basically, the attacker pays four times the block reward, assuming the miners are not cooperating. The miners are honest, in this case, with our base going to the penalty, and the miners get free base. And again, the point is the spammer doesn't just account to cover the penalty. For the very reason that I explained, the miner's not going to cooperate, so the miner's going to profit off the backs of the spammer. And this is why Big Bang actually has a much higher cost than just the penalty, although it's a block reward in this case. Now, if the attacker already has 51% and they want to do Big Bang as an add-on, then the additional cost is your block reward, because you're basically putting in the penalty. But without 51%, it's four times the block reward. So without a 51% attack.

A variant of Big Bang, which has been discussed in many cases, is a flood XMR. And the idea on that is to attack the ring signatures by flooding with enough transactions that you will overcome. You have enough, you know enough of the rings basically. Problem with that is, is that you need 16 times the transactions, the actual transaction rate to do that. There were some suspicions and some work done on this where members of the community suspected something was amiss, and they detected some organization or some entity pushing it. And what happened is they kind of went just to the penalty point and realized: "Oh, no, this doesn't work. We better try something else or go somewhere else." So it's deceiving in that you can get in cheaply into spamming Monero. But when you really get into it, then suddenly you get hit.

So let's get into an interesting question. One of the ideas in Bitcoin is, and it's right from the Bitcoin paper from Satoshi, is that you can turn around and eventually replace the falling block rewards in Bitcoin with transaction fees. And we can say, I can say categorically, that that will not happen in Monero. And the reason is that if you calculate what happens in your fee in Monero, it's just proportion to the block reward. But even more interestingly, so your total amount of fees you always get is going to be a function of the block reward. So the block reward is zero, so do the fees. The other thing is, as you make the Monero block size bigger, you have the option to scale at a lower rate. So what this tells us is, at best, the fee and reward for Monero, as you grow a block size, will stay constant, and it will likely drop. So you're not going to grow your way out of the Bitcoin security deficit.

I've had some interesting conversations with people in the Bitcoin SV community, and then they tell me all these great things, and I look at their fee and reward, and no, they're not replacing fees to the fee and reward, at least on a consistent basis. The best bet is actually the approach taken by Bitcoin Core, which is to say: "Well, we just keep the block size, well, and of course, we totally destroy its use as a transactional currency, but maybe we can keep it secure." Maybe. And that's the big maybe.

And here are some of the things that we've seen in high-fee cryptocurrency as a Bitcoin and Ethereum. If you look at the fee and reward - and I have sort of a link in there, bitinfocharts' great for that, because you can plot them out and look at it historically - what you'll find in Bitcoin is that it's, that you'll see little spikes when there's sort of a demand and surge on the network. And then it goes down to about 1%. And this happens in spite of, and there hasn't been a material change in spite of the halvings. So they're not even keeping up with the halvings. And what it's telling me is that fees are not gonna be replacing block rewards in Bitcoin ever. There's a lot of indication to this. It's called the Bitcoin security deficit.

In Ethereum, again, you see a similar spiking behavior, maybe a bit of a higher percentage, because it's very heavy use, and they've allowed it to grow. But still, you don't see an indication of replacing block rewards with fees.

I hate to say this. I mean, I may not see the fact that in 2014, 2015, I sold my Bitcoin from Monero over these issues. But I have some really serious concerns about the security of Bitcoin over the long term because of this issue. I'm also well aware that some of the Bitcoin developers have that concern. So there's a lot of concerns around this issue. It's a very delicate problem because the only way to solve it is to essentially do away with the most sacrosanct aspect of the Bitcoin protocol, which is the 21 million limit. So they're kind of between a rock and a hard place there. But yes, it's a tough thing to say. And it's not going to happen tomorrow. I mean the next halving in Bitcoin is going to put it in a par in inflation rate with Monero. So there may be a few more halvings on the road, but eventually there will be a problem unless something is done. That's my prediction.

So let's bend into the next thing, the Monero tail emission. Now, to my knowledge, Monero is the only coin that deliberately did this. Dogecoin put it in because it was a bug, and they kept it. But at least it saved them, because they had a bug in the code, and they kept it. It's a lot more inflationary than Monero. It's about 5%. Monero's tail emission was deliberately put in right very close after the start by the first core team. I strongly suspect a lot of miners were involved in that core team because a lot of people in the first core team were miners. I was not in the core team at the time. But they made that decision. They didn't believe in this thing and said: "Well, we're miners. We're just going to do this thing." And then they did something incredibly smart, is they set it just below the historical inflation rate of gold. Now I spoke a fair bunch of degree in Monoerotopia on this topic. And what it means is that Monero may be very close to optimal as to the rate of inflation. You're just below the inflation rate of gold, so you meet all the Austrian standards of Austrian economics, you exceed them actually, you don't meet them, you exceed them with respect to hard money.

So you can't claim this thing is an inflation printing out of control or whatever, but at the same time you maximize your security. The one thing I can say categorically, is if we were to move to a falling block reward model, Monero would become insecure and very vulnerable to spam and 51% attacks. If you want to price any attack against Monero, whether it's spam or 51% attack, it's always proportional to that block reward. That 0.6 XMR per block is what makes Monero secure and what makes Monero secure. Monero, very hard to spam.

So now we can talk about: okay, can we toughen it up a bit? And the answer is, there's a couple of things we can do. The first thing, and this is to tweak the medians. Now, remember the figure in MS that I talked about of 50ML to as the cap, as the surge factor. That could be reduced to 16ML. So you can reduce that median surge factor significantly to what is realistically going to be needed to cover surge factors from the Visa experience. And yes, you are allowing to go over if we've got sort of a superimposition of Christmas in need. I mean, the question Muslim attack, which I find really interesting, but because one is a solar calendar, and the other one is a lunar calendar, so theoretically, it's one point when the two will come together at one point. And you can still handle that, because you can go into that final penalty and go into 20 times or something like that. Even if it's a bit expensive, but you can deal with it. And then what you do is we push ML from 1.7 to 2. I know at the time this was controversial, but it will allow us to deal with the kind of surge factors that we, for example, saw in Litecoin when Bitcoin got into trouble.

One of the things I'm very concerned about, particularly in the current political climate in the world, is how will the Monero community deal with an attack on the hated fiat banking system? I know a lot of people in this community don't like banks and don't like the banking system. I wanna make sure that if somebody attacks it, a state actor, goes after Visa that the Monero network can stand on its feet, take some of the load, and keep running. And that means we've got to harden ourselves. That means we should get that extra computer, maybe get the extra bandwidth, maybe buy extra hardware to make sure you're gonna run bigger nodes. So we've had to be cognizant of the fact that an attack against the financial system is possible, and we have to be part of the solution. And that means tough work. That means rolling up your sleeves. It's not about: "Oh great, these bad bankers are being attacked." No, we have a problem. We have people that are gonna need to transact. We have a network that can do it. And as a community, we need to be part of that solution. And we can be. I mean, so that's one of the things I always consider in hardening Monero is consider the Litecoin scenario on a larger scale. So that's one idea.

The other idea is that we can put an ultra-long term sanity medium. Now a lot of members of the community would be a bit uncomfortable that: "Oh, I can just grow out of control" kind of thing. And one way to do it is to cap it at the existing, is to cap it at essentially an initial slow. And that means you double it roughly every two years, which is, in fact, what a 1 million block median would do with the formula that I put in. And what you do then is you do essentially the same thing that we're not doing with MS, but with ML. The sanity medium then becomes the factor for ML. And so again, you have MA as your penalty-free zone in ML and then you do the formula. And you do the recursive calculations, start ML, and you do it in case of a million or one blocks.

And so that's a way that we can do, we can harden a bit more. I consider this one a bit optional, but I think it might be members of the community that may feel more comfortable with something like this in place. And so it's something that I think is helpful. The median should be set generously, because I'll explain this in the next slide, on how we can go to deal with that, and that is, that is another way we can also address scaling issues, and that's node relay. Now, this is a topic that deserves a bit of discussion because there's also a misconception about node relays.

Node relay is nodes send transactions. Block transactions are unlikely to be mined by a miner. So what they do is: "Well, this transaction pays to lower fee, a miner is not gonna mine it, so I'm not gonna relate." And it makes sense. I mean, it makes a lot of sense. But it only works as a strong support for the policy. It does not work to enforce against the mine of the starving. So one of the common misconceptions is that both Litecoin and Bitcoin Cash, for example, have copied Monero and put notary fees. The problem with that is it's great to have a block reward, but the miners are cutting each other's throat because they're starving, they just can accept transactions directly and bypass the nodes. So node relay has to be done with something that's a strong ongoing, in the word ongoing, consensus in the community. It's a great way to deal with a flexible, changeable consensus that reflects what the community said that time. Yes, great way to do it. But it's not a way to enforce a hard consensus that many members of the community would not want to live with. Because they can always be over-driven by a miner. And the simplest way a miner would do it is they would simply put a website and say: "Well, we'll rebate you the fee", or "Give us your personal information, and we'll do it for free", or whatever. So that's kind of the thing.

What you can do, and there's been a lot of discussions for a lot of things, as if an ongoing consensus or something - yeah, not really - it's a great way to do it. And we do it with things like rounding of fees. If the fees don't meet a certain requirement or rounding, we won't send them. And the reason you do that is because you want to eliminate fingerprinting and improve privacy.

So it can be done also with block sizes. You have a generous block size and consensus. So you do the consensus level on the side of a big, on the generous side. And then you can tighten it down by nodes, particularly those who are understressing: "Well, I don't have the bandwidth, so I'm going to not relay as many transactions." And they selectively do it in a way that throttles the growth of the network. And then what happens is because there's less nodes, then you create a pricing market which will allow the few remaining nodes can say: "Okay, fine, I will do it", but there's a pricey market because it's less. And that can allow the network to sort of moderate a sudden growth for whatever reason. So this is kind of one way. Node relay is a very interesting topic. I'm going right into questions right now, right after this. There's been many suggestions in the community for using it for a host of different things. And as long as there's a strong consensus then that's a great way to do it. So it is another tool that can be used to harden Monero.

And now we can move to some questions and discussion.