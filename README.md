# Awesome Fork-Choice Enforced Inclusion Lists (FOCIL)

A list of articles related to FOCIL. The summaries are my own.

## Articles

### [State of research: increasing censorship resistance of transactions under proposer/builder separation (PBS)](https://notes.ethereum.org/@vbuterin/pbs_censorship_resistance) - Jan 30, 2022

### [Censorship Résistance & PBS](https://www.youtube.com/watch?v=XZJcZ05d-Wo) - Sep 7, 2022

### [Forward inclusion list](https://notes.ethereum.org/@fradamt/forward-inclusion-lists) - Nov 15, 2022

This article by Francesco introduces the censorship-resistance list (crList) as a means for proposers to combat censorship by forcing the inclusion of certain transactions. In this system, the proposer of slot N publishes a crList while the attesters of slot N+1 ensure that the builder of slot N+1 complies with it. After EIP-1559, the cost of censorship for a builder attempting to censor transactions by filling up blocks becomes exponentially expensive as the basefee increases exponentially. The article also cites the design goals of the censorship-resistance mechanism proposed by Vitalik.

### [Multiplicity: A Gadget for Multiple Concurrent Block Proposers](https://ethresear.ch/t/multiplicity-a-gadget-for-multiple-concurrent-block-proposers/14962) - Mar 4, 2023

This article by Elijah and Max proposes using multiple concurrent block proposers to enhance censorship resistance by moving away from a single leader and eliminating temporary monopolies. This approach raises the cost of censorship as the bribing agent now needs to bribe each of the leaders.

### [Censorship Resistance in On-Chain Auctions](https://arxiv.org/abs/2301.13321) - Jun 26, 2023

### [No free lunch – a new inclusion list design](https://ethresear.ch/t/no-free-lunch-a-new-inclusion-list-design/16389) - Aug 15, 2023

In this article, Mike Neuder proposes an inclusion list (IL) design where the proposer of slot N includes an IL in a block to constrain the proposer of slot N+1 while preventing free data availability (DA). The IL in a block contains transaction summaries and free DA occurs when a transaction in the IL of slot N is invalidated by a transaction in the payload of slot N. Since this can only happen between transactions from the same address with the same nonce, free DA can be avoided by ignoring the transaction in the IL, which is delivered as a P2P object.

### [Cumulative, Non-Expiring Inclusion Lists](https://ethresear.ch/t/cumulative-non-expiring-inclusion-lists/16520) - Sep 1, 2023

This article by Toni Wahrstätter introduces the concept of a forward-cumulative inclusion list (IL) design. In this model, a transaction included in the IL of slot N remains valid after k slots, provided it can cover the basefee of slot N+k. The motivation behind this design is to prevent a censoring validator from bypassing compliance with the IL, especially in cases where the validator has enough staking power to control consecutive slots.

### [Fun and games with inclusion lists](https://ethresear.ch/t/fun-and-games-with-inclusion-lists/16557) - Sep 6, 2023

### [EIP-7547: Inclusion lists](https://eips.ethereum.org/EIPS/eip-7547) - Oct 24, 2023

The first EIP on inclusion lists. Unfortunately, it is rejected due to some concerns such as transactions in the IL of slot N may be invalidated by transactions in the payload of slot N.

### [Unconditional inclusion lists](https://ethresear.ch/t/unconditional-inclusion-lists/18500/1) - Jan 30, 2024

This article by Mike Neuder advocates for the use of an unconditional inclusion list (IL) that brings agency back to the proposer in a PBS world by allowing them to express preferences over which transactions are included onchain. Each IL has a fixed gas limit and be placed at the bottom of the next block with its transaction order preserved. The article also explores the tradeoffs between unconditional and conditional ILs.

### [Concurrent Block Proposers in Ethereum](https://ethresear.ch/t/concurrent-block-proposers-in-ethereum/18777) - Feb 24, 2024

This article by Mike Neuder explores multiple concurrent block proposers in Ethereum as a means to improve censorship resistance and decentralization. It demonstrates that the cost of censorship increases linearly with the number of proposers in each slot while further examining potential approaches for adapting proposer boost to accommodate multiple proposers.

### [The more, the less censored: Introducing committee-enforced inclusion sets (COMIS) on Ethereum](https://ethresear.ch/t/the-more-the-less-censored-introducing-committee-enforced-inclusion-sets-comis-on-ethereum/18835) - Feb 29, 2024

### [Uncrowdable Inclusion Lists: The Tension between Chain Neutrality, Preconfirmations and Proposer Commitments](https://ethresear.ch/t/uncrowdable-inclusion-lists-the-tension-between-chain-neutrality-preconfirmations-and-proposer-commitments/19372) - Apr 25, 2024

This article by Julian Ma introduces the concept of chain neutrality and uncrowdable inclusion lists. It explores design approaches such as conditional ILs, COMIS, and mixed ILs to implement uncrowdable ILs. The article suggests that conditional reward to IL proposers, rather than block proposers, could enhance censorship resistance. It also argues that whether a protocol should intervene in block space allocation is a governance question, not one for markets to answer.

### [Anonymous Inclusion Lists (anon-ILs)](https://ethresear.ch/t/anonymous-inclusion-lists-anon-ils/19627) - May 24, 2024

### [The problem of 7547 and 3074](https://hackmd.io/@potuz/BkWngLly0) - Mar 26, 2024

This article by Potuz discusses the incompatibilities between EIP-7547 and EIP-3074, highlighting the need for a better design for the inclusion list. This ultimately led to the rejection of EIP-7547.

### [Fork-Choice enforced Inclusion Lists (FOCIL): A simple committee-based inclusion list proposal](https://ethresear.ch/t/fork-choice-enforced-inclusion-lists-focil-a-simple-committee-based-inclusion-list-proposal/19870) - June 20, 2024

In this article, Thomas Thiery points out the oligopoly in block production, which undermines Ethereum's censorship resistance, and introduces FOCIL, a mechanism based on a committee-based inclusion list (IL) design. In this model, each IL committee member for slot N produces a local IL and the aggregated local ILs constrains the block for slot N+1 to include at least a certain percentage of transactions from the IL aggregate in order to be validated.

### [AUCIL: An Auction-Based Inclusion List Design for Enhanced Censorship Resistance on Ethereum](https://ethresear.ch/t/aucil-an-auction-based-inclusion-list-design-for-enhanced-censorship-resistance-on-ethereum/20422) - Sep 13, 2024
