# Francois-Xavier Wicht

_**A Formal Evaluation of Privacy in Monero**_

[https://youtu.be/OC2LjmkMj8g](https://youtu.be/OC2LjmkMj8g)

---

_**Cayle Sharrock:**_ So yes, and this is a joint work with Zhipeng Wang, Duc V. Le and Christian Cachin.

So agenda for today: little intro first, then I'll introduce the model, the "Privacy-Preserving Transaction DAG". DAG stands for Directed Acyclic Graph. Privacy notions – I will pursue with privacy notions afterwards.

So for the intro, consider a repressive state with full control over the regular banking system, it may prohibit cash payments, establish a mass surveillance scheme and financial coercion.

Now, consider a resistance group. It's quickly deprived of any financial means and one of the few ways for it to thrive is to use a decentralized crypto.

Now, the repressive state knows that and scans and analyzes the blockchain history of said crypto in order to identify the main creditors and debtors of the resistance group, the addresses of the resistance group, and also the funds at its disposal.

Now, Leia regularly gives financial support to that resistance group. Now the question is: how much is Leia at risk if she uses a cryptocurrency?

To answer that question, we introduce a formal model. And this formal model is built upon the transaction-directed acyclic graph. I hope you guys can see. Yes, perfect. Because on the screen there, it's not quite it. So it's a graph. So it's composed of vertices and edges. Vertices are two types: states and witnesses. And the edges represent transactional relations between those.

What are states, what are witnesses? A state is an individual asset in the blockchain. And a witness represents the blockchain validation rule. For example, one of these rules is to make sure that to spend a coin, you have ownership of this coin. So it's about verification of the signature, for example.

Now we have several edge types. We have consuming edges. For example, think of spending a coin. You consume that coin. Now, if you transfer that coin to another person, you will produce a new state. So that's the producing edges. Now, in some cases, you might want to read a state without altering it. So for example, if you use a state as a decoy, you might only observe these states, so does observing edges.

I'll give you a little example of a transaction here. We have input state on the left, output state on the right. s0, s1 is input state and s2 is output state. We have a witness in the middle. A transaction is composed of exactly one witness. For example, this little transaction can be interpreted as Alice giving all her coins from two addresses to Bob. If she gave only part of her coins, there would be the production of a second state here to represent the amount surplus.

The properties of this graph is that every state is produced exactly once. This is the property of the hash function. Every state is also consumed at most ones. You don't want double spending, rights? G is weakly connected, means no orphans in the graph, and G has no cycles.

Now we also have quite handy mathematical notation that is a relational notation actually. So any path in a TDAG can be represented as a mathematical notation. Take the path from s0 to s2 is equation one, so s0 consuming edge, witness, producing edge s2, and the same we have for the path of s1 to s2 with an observing edge.

Now with this model, we can actually represent UTXO-based blockchains, account-based blockchains, but we also want to represent nullifier-based blockchain as we call them, so for example, Monero and Zcash.

But the problem is we don't have enough elements in the TDAG to actually represent those. Because like I said, we have some privacy in those nullifier-based blockchains. And if we don't see the state consumption and thus we add an edge, a masking edge, that appears as observing edge to any non-involved parties but actually acts as a consuming edge. For example, a state can only be consumed once, right?

We also add another component called a "nullifier" because we need to output additional components at each transaction to make sure that we don't spend an output twice. And in Monero, this is key images, for example. So this is depicted with the diamond here. So we build up on the TDAG and we add masking edge. And we add also these nullifiers here. And this gives us the privacy-preserving transaction DAG or PDAG.

So now I have the PDAG defined. I can dive into the privacy notions. So first I'll give you a glimpse of the adversary model. Then we'll talk about untraceability and if we have time, unlinkability.

So we denote by Π the blockchain at hand. The adversary A is passive, only observes. It's computationally unbounded, but we also assume idealized cryptography, and the adversary tries to compromise any of the privacy notions, namely untraceability and unlinkability.

So overview of untraceability. So untraceability means roughly that for each incoming input state, any of them is equiprobable to be consumed. So the adversary only sees ambiguous edges, so either observing or masking edges. So ambiguous edges is the union of masking and observing edges. But the adversary tries to lift this ambiguity. So he tries to guess which one of these edges is actually a masking one, is actually a consuming one.

So here we see well, for the adversary, it has only one third of probability to actually guess right. So that's for a single transaction. We actually argue that this probability can be decreased if we look at the full PDAG. So follow me there.

If we have three transactions, we argue that we can actually rearrange them in the bipartite graph. And then that's the view of the adversary on the right. That's the ground truth on the left. Right? Now we use the work of Vijayakumaran and Egger et al. to actually take the core. And the core is the union of all the maximum matchings. Why do we take that? Because actually the state consumption takes place only on one maximum matching. And the core is actually the union of all the maximum matchings. And it is a subgraph of the bipartite graph that I just showed you, only with a subgraph of the edges.

So in a nutshell, the adversary, when it computes the core, it's able to actually prune some edges. So reduce the untraceability set. So here, for example, let's go back to the example I had before, we have in color two maximum matchings, red and blue, and then we have a violet edge that's part of both maximum matchings. So we are able to actually prune those two edges that goes to w3 that are dotted. So actually there's full de-anonymization here happening.

So this is well-known research here that I'm talking about, but this is to formalize actually untraceability. So untraceability here is actually important because if the core of G is not equal to G, well, the adversary is able to prune some edges, reduce the untraceability set. Otherwise, if the core of G is equal to G, takes the smallest witness, and there's random guessing on that witness. Well, the smallest witness by that, I mean the witness with the smallest indegree, right?

And I have my first definition here – "k-untraceable transaction". If a transaction is the subgraph of the core, that is really important actually, and with no consuming edges, with only ambiguous edges, and those ambiguous edges must be of at least two, and we have this k, this k represents the amount of ambiguous edges. so k-untraceable transaction here. So that's only for a single transaction. Let's talk about the full PDAG, right? Because the PDAG is actually a mirror to a blockchain execution.

So now take the full PDAG. The PDAG is actually untraceable up to its weakest transactions, so to the smallest k. And also all the transactions must at least be k-untraceable for the PDAG to be k-untraceable. Because if there is one consuming edge, one visible consuming edge, well the full PDAG is not untraceable.

And now let's talk briefly about Monero. We upgraded the ring size to 16 pretty recently. Oh no, is it recently? Or was it one year ago? Sorry, one year ago, thanks. And so with no doubt here, if the core of G is equal to G, we have that k is equal to 16, so Monero is 16-untraceable.

And now let's briefly talk about Zcash. Zcash – we have a shielded pool, transparent pool, but we are interested in the shielded pool here. And in the shielded pool, untraceability is provided with zk-SNARKs. So we don't have a list of public keys for the untraceability set. The untraceability set is actually implicit. We have any previously produced states as the untraceability set. And so the PDAG of Zcash, if the core of G is equal to G, is actually the smallest witness with the smallest set of previously produced states for witness. So apparently yesterday there was a talk about increasing the untraceability set of Monero to this kind of technology with full membership proof. So this might be the future of Monero here, this definition.

So now, I don't know how much time I have, but the next privacy notion is unlinkability. Unlinkability is… so we have unlinkability if we are not able to link two addresses to the same entity. And those two terms are actually quite close – untraceability and unlinkability, but they are actually completely different.

So, now we define to abstract the linking and abstract this notion of entity, we define an equivalence relation L on the set of states. So here we have, and because the adversary tries to partition the set of states, right? Now we have a refinement of this linking relation. This is the address relation because in Bitcoin we can have like multiple states with the same addresses. In Monero it's not possible.

And now for the adversary, this is the matter of identifying the states that belong together, but the adversary doesn't have the L. It only has an inferred relation tilde L. L tilde, sorry. And so it tries to compromise unlinkability with this inferred relation.

And now we can actually... This inferred relation refers directly to the heuristic of the literature. And we can, with our PDAG notation, actually describe those heuristics. And you see here that the most common heuristics that we see in Bitcoin, the multi-input heuristics, because in Bitcoin, if you use multiple addresses, at some point, you will need to merge them back, so to spend your output together and that pattern is noticeable. And this was actually already described by Nakamoto himself. So we can see here in the third equation that for all pair of states in an input state, they might be linked with the inferred relation.

And now, like I said, the adversary tries to compromise unlinkability with this inferred relation, but this inferred relation might not be right. So there might be a dichotomy between L and L tilde, right? And this dichotomy, because if the adversary puts you in the wrong equivalence class, you actually have more privacy, right? This dichotomy is actually a source of privacy. And so the gray area here is actually the unlinkability set.

Now the unlinkability set, the size of this unlinkability set is not the full story. For example, if I have a set difference of one, but here we have an unlinkability set with inferred relation 100 and the ground truth with 99 is completely different, because we have this probability of 0.98 compared to a probability of one third of guessing right. So we need to actually count the ratio of unlinked pairs. And this is what I call the "unlinkability score". The unlinkability score is the ratio of unlinked pairs over all the possible pairs.

And so we have a u-unlinkable state if that u is actually bigger than zero. And if this u is actually one, the state has full privacy. And of course, same logic as before, we have a u-unlinkable PDAG if all the states are at least u-unlinkable.

Now, let me just quickly talk about Bitcoin with CoinJoin. CoinJoin actually counteracts this multi-input heuristic. And so let me give you an example. We have in color the states that belong to the same entity. And a multi-input heuristic would put all of them in the same equivalence class. But for s0 and s1 and s2 and s3, since they are identified among two, well, you have an unlinkability score of 10 to 21. As far as s5 and s6, the same entity, 6 to the 21. So the more contribution you give to the input states, well, the less unlinkable you are.

So here I have a lemma also for this unlinkability score of CoinJoin. Now I'm going to go straight up to this conclusion.

I think unlinkability score, this maximal unlinkability score can be kind of leveraged. And we see that with CoinJoin it can be leveraged. And I think it can be called as the maximal exploitable privacy. It could be leveraged by a wallet or blockchain clients. So any heuristic can be counterfeit this way in my opinion, right?

So conclusion can we define other notions with our model? Can we compare all the systems? I believe so. And how much privacy is enough privacy? So we saw this k here – how much is enough right? So we think it might be enough at some point, right? Thank you for your attention.
