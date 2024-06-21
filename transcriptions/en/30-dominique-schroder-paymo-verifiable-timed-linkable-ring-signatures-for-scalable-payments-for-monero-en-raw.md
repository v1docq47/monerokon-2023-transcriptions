# Dominique Schröder

_**PayMo: Verifiable Timed Linkable Ring Signatures for Scalable Payments for Monero**_

[https://youtu.be/1TYbtM9mgMI](https://youtu.be/1TYbtM9mgMI)

---

_**Dominique:**_ Hello everyone! Many thanks for coming and also for the organizers of this amazing event.

Yeah, I'm a cryptographer and we are interested in bringing cryptographic schemes, of course, to the practice, so to the real life. So we are very excited in getting information from the community, right, to understand where are your needs, and where we can actually develop novel and practical solutions.

So I'll have the pleasure to talk about a cryptographic primitive that we call "verifiable timed linkable ring signatures". I will walk through you step by step what this is, and where we see the applications of course are building payment channels in Monero with the advantage that we don't need to touch the transaction scheme.

So this is joint work with my students, Aravin who's currently at NTT Research, Giulio who's at the Max Planck Institute and Fritz who's still working with me, the other two, unfortunately graduated in the meanwhile. No. Fortunately, right, but whenever they're amazing. They need to leave.

So let's start with initial problem, right? So why do we want to do payment channels? There's at least three reasons for it: of course reducing transaction fees, increasing the speed and of course saving energy.

Monero doing much better in terms of transactions as you all know then for example Bitcoin, right? What we have is that we find blocks roughly every two minutes, confirmation are roughly 10 blocks, which means the confirmation time is about 20 minutes. And of course, if you want to buy something in general, whatever is faster is better.

Energy is in everyone's world. We should save energy wherever we can. Of course, the proof of work is pretty good in Monero, but the less transactions, the less blocks we need to put on the chain, of course we save energy. And therefore, our whole motivation in general is to reduce the number of transactions that actually go to the chain. Of course, the alternative approaches like proof of stake, but as you all know, proof of stake comes with their own problems, and we often see a centralization of stakes, so the question is, is it a decentralized system? Many people are working on proof of useful work, so how can we use these individual proof of works in a better way? Again, these are open research problems.

So we're interested in this work for at least these three reasons: reducing transaction fees, faster transactions in general, and saving energy.

So what I will do next is I will give an introduction in what are payment channels in general, how do we use them, what are ring signatures, and of course linkable ring signatures. I will not focus on the confidential transactions as they're used in Monero, just to keep the scheme simple enough, right? You can upgrade it for the main idea is this will be sufficient. We will talk about verifiable time signatures and this brings us to the question, how can we embed the time lock that we have, for example, and the Bitcoin scripting language cryptographically? How can we realize that? And the green parts are essentially the novel stuff, the verifiable time linkable ring signatures, efficient constructions, how can we do this? And finally, how do we integrate this into Monero without changing the transaction scheme?

So let's get started. Of course, what are off-chain payments? So the basic idea is the following. The main idea is to reduce the number of transactions that actually need to go to the chain. And the payment channel, I'll do this high level and we will dig a little bit deeper step by step, a payment channel is one transaction that opens the channel. Then there are many transactions going on between the participants that are all off-chain. And there's one transaction that closes the channel.

So the challenging problem here is the following, and I'll start with a little example in Bitcoin, the challenging part here in general is that you have somehow to lock a certain amount of coins. So there's a transaction that says: I will lock an amount of coins, and this is the amount that we can transmit in the meantime. And for security reasons, there must be a possibility to send this money back. Right, so for example, if Alice says: "I'm opening the channel with a capacity of 10", and Bob, for example, says: "I'm not interacting with you", then without this time lock, this money would be locked forever. And the time lock essentially says: after a certain period of time, if nothing happened, then the money goes back to Alice. We will see this shortly more in detail.

And to close this channel, we will essentially create some sort of multisig that says: that's the final state of the channel where we both agree on. So the initial transaction here to open a channel with a certain capacity and the final transaction on the chain that says: okay, we use the following capacity in that way.

Okay, so let's start with ingredients. I mean, signatures is clear for everyone, right? Ring signatures as well, but let's recall them briefly. So the cool thing of a ring signature is that you can essentially sign a document, but the linkability to the sign is unclear. In other words, whenever you build your ring with the certain set of members, then the only thing that the person that verifies the signature knows, it was one out of these people, but you cannot tell who it was. That's the property that is known as anonymity.

Building a cryptocurrency purely from this assumption is not enough, right? And why? It's clear that essentially Alice, if there would be no additional property, she could build two different rings and perform a double spending attack. And this would be, cannot be detected in this setting, right? Because you just know it was one out of these guys. And this brings us to the linkable ring signatures, which are essentially used in a variant and Monero as well.

And the idea is super nice and elegant, right? So you still have the anonymity property, right? So you still don't know who signed it, but in case that you're signing a second transaction twice, in other words, if you try to perform a double-spending attack, then this double-spending can be detected. Very beautiful.

Okay, so now we are taking the next component that we need, and this is called a "verifiable time signature". Initially, these primitives were found over 20 years ago, and cryptographers didn't look at them for quite some time. And then we realized that we can do stuff with them that we cannot do with them otherwise, right? So for example, this huge area of fairness, which says, for example, can we compute a signature in a fair manner? It's impossible in general, but with these primitives it works.

So what is it? Well intuitively it behaves like a regular signature, which means, right, so Bob can create a signature. But it has this additional cool property that you can commit to the signature in a very fiber way. So think about it, you can put your signature in a box and give a proof, right, so the proof will tell you: there is a valid signature in this box. And the interesting property is the second one. There is a defined cryptographic mechanism to open that box within a certain number of computations. It means that there is an opening called force opening, and after T steps of computation, you can get the signature.

Okay, so these are the properties: Time Privacy. Before everything, before this time T, everything stays in. So you can't just see it. And Verifiability — you can be sure whatever is in the box is, in fact, a valid signature. So the verification goes within the box. And the very cool property is taken from the Time-lock Puzzles that essentially says: after the time T, you definitely get back a valid signature.

So the basic idea here is that there is a sequential squaring operation in RSA group for which we just know the only way to compute this are exactly T steps. So you can choose your bound T with respect to the computation that are needed in these groups. And the whole idea will be to replace the time lock that Bitcoin uses as a script in a cryptographic way through the time lock signatures.

Okay, so let's put everything together. As I said, fair computation is impossible in general, well, in certain models. But of course in the setting of blockchain with these primitives we can do it.

So what did we do? So we essentially embedded both parts together, which means we introduced the notion of verifiable timed linkable ring signatures. So we embedding this property cryptographically into the scheme. We found a very efficient construction. And this allows us to integrate it inside of Monero without changing the transaction scheme. And of course, I mean, the argument is the same, right? Scalable, cheap payments that save energy.

So let's take a look how this actually works. So from a very high level, and I give you the reference to the paper, the interface looks very similar to the classical time signature scheme. With the main difference that here we have a linkable ring signature scheme. So you still can commit to the signature. Now it's a linkable ring signature. You can verify that you have such an object inside of this box. And you can definitely open it after performing T steps of computation.

So let's start with a naive approach and see if this is enough, if we can directly obtain payment channels. Well, this is our payment channel. And as I said, we are digging a little bit deeper into how they are constructed. So to open the payment channel, both parties are actually creating a joined address, which means from this address, we can only spend if Alice and Bob sign it. And it has the capacity of 30 coins, and the channel should last for time T. Right, so here this expiration time, of course, in the first step would be realized with time logs that we, for example, have in Bitcoin.

And now these parties can interact between each other, and they can update the channel, which means they're creating transactions that essentially say: pay one coin from this joint address to Bob. And they do so, for example, for let's say 30 transactions. So these transactions here are between both parties, and this transaction here is the one that is sent to the chain. Each transaction would be signed by the linkable ring signature in Monero. Again, we are omitting the confidential part to make it easier. And to close the channel, Bob will essentially post, ideally, the last transaction on the chain, and this would correspond to the final state of the challenge. So in other words, what we get is if we perform 30 payments, we just need two transactions that go to the chain.

Unfortunately, right, there's no time log script in Monero, and therefore this direct and naive realization doesn't work. And this is where our VTLRS kicks in, and they would essentially look as follows. I mean, somehow we need to embed this functionality without sending it directly to the chain, and it would work as follows.

These both party, they create a refund transaction, and this refund transaction says: pay 30 coins from this joint address to Alice. So Alice initializes the channel, and she wants to make sure if something goes wrong and get her money back. And therefore, this initial payment here, this capacity, will be sent from the join address back to Alice.

And now Bob will essentially pack this joined address here in a time-lock puzzle. Right, so this time-lock puzzle will then make sure, if we choose T correctly, that Alice can recover this transaction if anything goes wrong and post it to the chain in order to get her money back.

And on the other hand, Bob, right, I mean they're performing this payment channel that we saw before, he needs to make sure that he's pushing the correct state of the channel before time T, otherwise the address is gone. Okay, so Alice starts solving the puzzle, and if the final transaction wasn't posted to the chain, she gets her money back.

So how can we actually do this directly in Monero? And as I said, we are not looking at the confidential transaction just for simplicity, but it works exactly the same way.

So as you know, right, this is the basic structure where the secret keys is an element x and the public key is g to the x, and we are essentially choosing the ring as always, let's say, with n participants. This is then the easier realization where of course the first part is the linkability tag that we need to detect the double payment. And here inside, right, that's the loop that goes over all the participants, and we are essentially creating some aggregated form of a Schnorr signature that we can then verify in the end.

So somehow we need to find a method to embed our idea of the time-lock puzzles inside of this structure. And the ideas that we essentially used are based on prior work that we published at CCS 2020, where we were wondering how can we improve the efficiency of time signatures. And we found many constructions, so based on Schnorr, ECDSA, and BLS.

And the basic idea is essentially the following. We take a signature that has these beautiful algebraic properties that we need. And what we then do is we secret share this value with a t-out of-n Shamir secret sharing scheme. So for those that, I guess most of you know what this is, right, so you split your secret in several parts. Each part doesn't reveal anything about the secret, which would be the signature, and you only need the threshold, this is the value t. As long as you get t values back, you can reconstruct original value. And then our idea was to secret share each, basically to time lock each of these secret chairs, and to provide a proof of correctness that essentially says: I'm proving, and of course not interactively, that t – 1 of these puzzles were constructed correctly. So you will need this proof in order to make sure that the guy who created this share is not cheating. So what you will obtain is essentially commitment and proof π, and the proof π corresponds to the open puzzles.

Right, so this is the idea. And we will take a closer look at the structure, right? This is the proof, the unopened puzzles, and the open signature shares.

And now the nice idea is essentially, I mean, how would you do this verification and false opening? You first check that all signatures are valid, and this you can do very efficiently because it's a Schnorr signature, or a Schnorr type signature. In the next step, you would start solving the puzzles in order to get one more share, right, that's sufficient, because you've got t – 1 values before, and then with these t shares, you can actually reconstruct the signature.

And here we are relying on other work that by Aravind and Julio that appeared at Crypto19, the nice thing is that these puzzles are homomorphically, so you can just compress them and it works quite efficiently.

So how do we embed this? Well the idea is that if we take a closer look on the structure of the signature, then instead of giving out this value as zero directly, what we will give out is a commitment. And this commitment will have exactly the structure here. And with this structure here, we can essentially nicely embed this into our puzzle. And this follows essentially previous ideas that I just mentioned before.

Regarding the performance for a theoretician like me, right, it sounds awesome. So we implemented this, of course, in a local testnet. And the commitment time to compute the commitment is around 568 milliseconds. Verification time is about 467 milliseconds. I'm seeing I'm running out of time. But in summary, if you essentially look at the computation times also considering different variants of latency, then we essentially got almost 94,000 signatures per CPU core in transactions per CPU core in two minutes.

Okay, so that's all. I'm over my time. I thank you for your attention. I hope that I could catch everyone, and I'm looking forward to questions. Thank you.
