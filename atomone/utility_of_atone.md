_NOTE: this article contains forward looking statements that should be
interpreted as a proposed roadmap for AtomOne, rather than as promises by the
authors._

# The Utility of the ATOM and ATONE Staking Tokens

## Introduction

Tendermint pioneered POS (proof-of-stake) in 2014 (by solving the "nothing at
stake" problem) using classical consensus techniques originally developed in
the 1980's for fault-tolerant missile defense systems. The Cosmos Hub was the
first blockchain to launch on Tendermint in 2019, and described a network of
IBC (inter-blockchain communication) connected blockchains. IBC as an acronym
was coined by us for Cosmos. Cosmos in turn spurred a resurgence of interest
and capital into consensus research worldwide. Today there are thousands of
proof of stake blockchains.

To distinguish between Cosmos, the internet of blockchains, and the Cosmos Hub,
the first blockchain and hub for Cosmos, we will refer to the Cosmos Hub in
this article as Gaia, the name of the Cosmos Hub program.

### The Dual-Token Model

In the original Cosmos Hub vision [ATOM was not meant to be a monetary token](https://allinbits.com/blog/nwv-to-prop-848-atom-must-not-be-money/) or
fee token, but rather ATOM was a new class of token that we dubbed the "staking
token" ATOM was designed to inflate at a rate between 7% and 20% annually and
the newly created ATOMs distributed back to the stakers pro-rata, effectively
serving as punishment for not staking, while intentionally making them
unsuitable as a token for payments or savings. 

A separate fee-token was proposed for Gaia that would serve as the
fee-token which would not suffer from ATOM's continuous inflation. ATOM would
be like proof-of-work mining hardware, while the fee token would be like
deflationary bitcoins, and the fee-token is not concerned with consensus or
chain governance. This distinction between staking-token and fee-token is
called the "dual-token model". (see [Cosmos Token Model](https://github.com/cosmos/cosmos/blob/master/Cosmos_Token_Model.pdf)
which clearly suggests the dual token model and its advantages).  

The dual-token distinction is especially important for Gaia and AtomOne as an
IBC hub because a double-spend attack on the hub can steal IBC pegged tokens on
all the chains that connect via IBC to the hub chain. With a single-token model
there is no restriction for whales to take over the consensus of the hub; and
it is assumed that the singular token is widely distributed and easy to
acquire. In dual-token models with separate staking-token and fee-token where
the fee-token cannot be converted to staking-tokens (except via the normal
exchange mechanisms) the fee-token holders cannot conduct a hostile takeover of
the staking-token distribution unless the staking-token holders wanted to sell;
and even if they did sell, in the process of buying staking-tokens the attacker
would incur a significantly higher cost in price and time.

Despite popular demand Gaia's fee-token has not been implemented
(but [is for AtomOne](https://github.com/atomone-hub/atomone/pull/57))
since any IBC-pegged token can serve as the fee token anyways, and
instead many in the Cosmos ecosystem developed LS (liquid staking) derivatives
as a convenient way to dodge ATOM's inflation, even though LS ultimately
undermines the security model of staking-tokens. Furthermore with the
["ATOM 2.0" proposal](https://forum.cosmos.network/t/proposal-82-rejected-atom-2-0-a-new-vision-for-cosmos-hub/7328)
and subsequent proposals there was and still is a push to make the ATOM token
less of a staking-token and more of a monetary token, sometimes pitched as
"internet capital", or generally something with lower inflation rate such that
it would have "more utility". Simultaneously, there is a widespread sentiment
that "ATOM has no utility".

### Introducing AtomOne

For these reasons we and many supporters of the original (Atom 1.0) vision have
forked Gaia into a new chain named AtomOne. Instead of Gaia's ATOM token
AtomOne has the ATONE token. And while LS derivatives are banned for the ATONE
token, AtomOne will finally support the PHOTON fee-token which can be acquired
by (one-way) burning ATONE tokens. AtomOne has a
[constitution](https://github.com/atomone-hub/genesis/blob/main/CONSTITUTION.md)
and improved structured governance model that will ensure a clear division of
roles: PHOTON serves as the exclusive fee-token for transactions across all
shards, IBC fees, and ICS/VaaS payments, while ATONE powers governance and
staking. ATONE can be burned to PHOTON with a capped supply of PHOTONs,
ensuring economic balance and long-term scalability, but PHOTONs cannot be
converted back into ATONE tokens.

AtomOne and Gaia are "coopetative" just as peer validators are, and together
we hope to fulfill the multi-hub vision as originally described for Cosmos and
also as described later. The multi-hub model is especially important to give
users freedom of choice, to prevent centralization of the Cosmos, and to test
innovations in isolation for the sake of security, as Litecoin and many forks
also did for Bitcoin.

## The Problem

ATOM & ATONE are for staking, not for paying. Anyone complaining about the high
inflation rate of the ATOM & ATONE token is fundamentally misinformed about its
purpose and tokenomics. ATOM & ATONE does have utility as a staking-token, but
it depends on a large volume of transactions (whether DEFI or not). The "spam
prevention" or "priority" transaction fees may be small for each transaction,
but they add up significantly with scale. This is why Gaia and AtomOne offer
ICS. ATOM & ATONE stakers earn a portion of the transaction fees not just on
the hub, but across all ICS shards. Whether the transaction fees across the ICS
shards are paid in PHOTON or any other third-party token, ATOM & ATONE stakers
earn them as income. (The ATOM & ATONE inflation on the other hand should not
be considered income, but rather a penalty for not staking. See the [staking-token tax proposal](https://github.com/atomone-hub/future-security-agency/blob/main/WIP/002-staking-tokens-irs.md) and also [this blog post from Germany](https://patrick-wieth.medium.com/why-i-did-not-pay-taxes-on-staking-rewards-and-why-it-makes-sense-b6cc3b0ec4e).)
In short, ATOM and ATONE's only utility should be staking, and other utilities
should be offered by ICS hosted applications.

### Cosmos Needs Viral Dapps

The problem is that there are no applications in the Cosmos ecosystem that have
thus far saturated a blockchain's transaction capacity to the degree that
horizontal scaling is necessary. The Cosmos ecosystem has the CosmosSDK, as
well as various VM smart contract platforms based on the EVM as well as
CosmWASM yet we don't have a killer consumer app. Even [Osmosis's
blocks](https://www.mintscan.io/osmosis/block) aren't saturated.

This problem is not just in the Cosmos ecosystem. Today, the userbase of crypto
has not been significantly increasing. Bitcoin has the same number of [unique
addresses](https://www.blockchain.com/explorer/charts/n-unique-addresses) seen
today in 2025 as was seen in 2017, and this metric is trending downward.
Ethereum has rollup chains but yet the main chain is saturated in gas at 15tps
(transactions per second), and of rollups, Coinbase's Base today runs about
100tps, and another popular L2 called Aribtrum while has a higher potentiak
throughput capacity, runs today at about the same number of tps as mainnet
Ethereum. The problem isn't transaction throughput which is clearly offered by
rollup chains, but rather there hasn't been a killer app in Ethereum in a while
since stablecoins and NFTs. Solana has one of the highest transaction
throughputs, about 400tps (not the advertised 4000 which includes consensus
messages), but their smart contract system is optimized for high throughput
financial transactions and relatively unsuitable for non-financial dapp
development. 

### The Three Layer Cake

The real bottleneck for realizing ATOM & ATONE's ultimate utility are:
 * A consumer application that gains viral widespread adoption
 * A better smart contract platform that can enable the above
 * A permissionless way to launch ABCI containers that can support any kind of
   smart contract platform.

These three points correspond to the "3 layer cake" model of the future
blockchain stack, each one depending on the layer below it:
 * Layer 3: smart contract dapp
 * Layer 2: smart contract platform/VM
 * Layer 1: ICS/VaaS hosting provider (defined later)

The next generation of viral consumer applications will probably be built on
next generation smart contracting platforms that offer significant advantages
such as succinctness, general expressiveness, and object-oriented encapsulation
over those that already exist today. Even if such a platform is not developed
within our ecosystem, ICS/VaaS hubs can benefit from external developments by
offering the best scaling solution; after all, it isn't Amazon web-servcies nor
any digital cloud provider that develops the applications that run on these
platform providers--it is the general public.

## Layer 1: ICS/VaaS Hosting Provider

Gaia offers [PSS (partial set security)](https://cosmos.github.io/interchain-security/features/partial-set-security)
which allows the Gaia validators to permissionlessly participate in 
validating new chains. This has a clear advantage over the previous initial
release of ICS which required Gaia governance to approve of new chains
secured by the same validator set, requiring much coordination and making the
adoption of new applications on Gaia ICS a political endeavor.

### Fractional Staking is Dangerous

While PSS makes validator participation permissionless, it suffers from
unbalanced "fractional staking" where one ATOM staked on one validator may be
used as staking collateral for a different number and set of chains as compared
to another ATOM staked on another validator. There are no bounds on how many
chains a validator can validate for with the ATOMs delegated to it, so a subset
of validators could validate on PSS chains with the intent of attacking all of
them simultaneously. In order to prevent honest validators from foiling this
plan, the malicious validators can participate in chains that don't offer
positive ROI for validators (except when the chain is attacked). Therefore, PSS
is not secure in the absence of more controls.

In order to achieve secure scaling, individual validators should not have
freedom in choosing which chains to validate on, unless additional security is
staked independently of the original ATOMs staked on the hub. In short,
permissionless fractional staking is in general insecure. The fractional
staking of ICS without PSS (where all validators secure all ICS chains) can
also fail (if say a significant portion of the validators were to conduct an
attack and steal all IBC pegged tokens), but the key metrics (such as the total
value of ATOMs staked versus the potential gains from IBC token theft) can be
measured more easily, and unlike PSS an arbitrarily small subset of malicious
validators could not conduct an attack independently of the whole validator
set. Furthermore, competition among hubs can help ICS applications to migrate
to greener pastures with better security (more reputable validators, more value
staked vs available for theft), while the default assumption of PSS is that the
ICS application has no control over its validator set.

### Permissionless Deployment

What is needed is not permissionless validator participation (we need the
opposite), but rather permissionless application chain deployment. It should be
easy for any developer to develop a blockchain application that speaks the ABCI
protocol (such as an EVM chain or a CosmWASM chain) and package it into a linux
container, and upload it to the hub to be deployed as a new shard chain secured
by the same validator set as the hub. We call this VaaS short for "validation
as a service". It is a decentralization of the Amazon PaaS (platform as a
service) web services model; just like you can simply deploy a linux container
image to an Amazon EC2 server, you should be able to deploy one to Gaia and
AtomOne.

(ICS stands for "interchain security" but this term is a bit misleading when
referring to the model where the same validator set must secure all application
chains, as arguably there is only one "chain" which is composed of many
horizontal shards. To distinguish we introduced the acronym VaaS, so instead of
an ICS hub we can refer to a VaaS hub where every shard is secured by the same
validator set as the root.

There are varying degrees of permissionlessness in the VaaS model, but in the
most permissionless form a chain application can be deployed by anyone with one
"click" (or one transaction) and will run indefinitely for as long as the chain
application pays the fees due for the amount of storage, compute, and network
requested by the chain application. The chain application may have a governing
body that makes decisions on behalf of it; such as its storage, compute, and
network allowance; or how to deal with bugs and failures; or whether to migrate
to another VaaS provider. Or, the chain application may not have any governance
of its own, in which case the VaaS hub governance may intervene on behalf of
it, or not, depending on the SLA (service level agreement) and constitution of
the VaaS hub.

AtomOne will not offer Gaia's PSS as is, but instead adapt the existing ICS
and PSS implementations to support the VaaS model of security. And instead of
permissionless validation, AtomOne will offer permissionless deployment. This
is the next significant technical feature that will be worked on for AtomOne
after PHOTON gets deployed. This will make it easy for anyone to deploy new
CosmosSDK developed chain applications, an in particular those chain
applications that offer new and existing smart contract programming
capabilities.

## Layer 2 & 3: Smart Contract Platform and the Killer Dapp

Ask yourself how many people you know that really use blockchains and crypto,
and what they use them for. Most blockchain applications are DEFI applications,
and most of them are about speculation, especially of meme-coins.

### We Need Decentralized Social & Knowledge Systems

Is it that blockchains have no more utility than for DEFI applications that
already exist? The opposite is true. There's nothing quite as needed today as
decentralized trustless social and knowledge-base systems.

People who speak against the official narrative are being deplatformed.
Algorithms are making recommendations in unknown ways, and censoring
information. AI is being abused with hundreds of billions of dollars flowing
into its investment, and we have to trust centralized companies to not just
defend against external AI bot threats, but also trust them not to abuse AI
internally, when its incentivces are not aligned with these goals, as proven
with Facebook's Cambridge Analytica and similar scandals. In more recent times
we have seen through TwitterGate the covert involvement of government backed
censorship programs; and even Google which blindly follows the recommendations
of the WHO which censored critical information about the origins of Covid19 and
the safety and efficacy of mRNA gene therapies marketed as "vaccines".

With centralized web services you don't have a choice on what you consume.
Outbound links to competing services are restricted, limiting information
availability and keeping the user within the curated walled garden.

Controversial but important content is downvoted and flagged by bots, or
deleted by the moderators of the channel, subreddit, or group. If the
channel/subreddit/group doesn't moderate it themselves, the moderator set is
infiltrated as Ghislane Maxwell did to the /r/worldnews subreddit's moderator
set. If the channel/subreddit/group cannot be subverted in this way, it is shut
down. Controversial content won't show up as suggested content because they are
filtered by recommendation algorithms and blacklists that are not publicly
revealed. Even when you find the information you want, any associated comments
are full of shills and now AI bots to influence the public's opinion. If they
don't sway your opinion, they sway other commenters' opinions, and the people
around you.

Even Wikipedia co-founder Larry Sanger recently claimed that Wikipedia can no
longer be trusted.

> "Wikipedia made a real effort at neutrality for its first five years or so,
> and then **it began a long, slow slide into what I would call 'leftist
> propaganda'.**
> ...
> **They've gradually gotten rid of all blogs, and recently they got rid of
> almost all conservative news sources as sources for their articles**. So as
> the news media has shifted and as the establishment has shifted to the left,
> the content of Wikipedia has synced." - Larry Sanger. ([source](https://odysee.com/@PrinceActarus74:a/IMG_0773:67))

This method of control -- introducing bias by only using media companies that
favor 'leftist propaganda' which include just about every major media
conglomerate company, is also the method by which AI based on large language
models will be biased and used to control its consumers. Regulations such as
those [proposed by the
FSA](https://github.com/atomone-hub/future-security-agency/blob/main/WIP/001-reproducible-ai.md)
can help mitigate this risk, but this is impossible in the current political
climate even while sweeping reforms are being introduced, because nobody in
politcal power actually intends to solve this problem, because their power
depends on the problem.

Clearly we need decentralized services more than ever, but the reality is
despite all the interest in cryptocurrencies, these non-DEFI dapps have not
succeeded in gaining adoption.

### We Need Better Smart Contract Platforms

The main obstacle is the immaturity of the space; the difficulty of "dapp"
(decentralized application) development and the limitations of smart contract
systems. Existing object-oriented general purpose programming langauges such as
Go are better suited for coding say social communication applications. Not only
modern langauges easier to program in, they are better suited for data-centric
applications (whereas existing smart contract systems are not), and popular
general programming languages already have a wealth of libraries to build on.

Twitter succeeded because it leveraged a language suitable for rapid iterative
development with a rich library to rely on. For a smart contract platform to
succeed in supporting new social applications, it must allow developers to
leverage the wealth of existing libraries. 

WASM-based smart contracting systems are useful and well deployed, but the
primary language for developing WASM contracts is Rust, and while Rust is fast
and memory efficient, it is not a great prototyping language and the barrier to
learning is relatively high. Reddit was written in Python, a modern general
purpose language with low barrier to entry. Twitter was originally written with
Ruby on Rails, but later switched to Java for performance reasons. It probably
would not have succeeded if it started off with Java, but it could afford to
migrate to Java once it reached scale.

While this is perhaps one of the most difficult challenges of computer science,
as evidenced by the slow progress of computer programming langauge innovation
spanning over decades, the problem is solvable; and Gno.land proves it. To see
how and why, and how Gno offers "seamless interoperability of untrusted user
programs" unlike any other smart contract systems, check
out this [2024 Gophercon talk on Gno](https://github.com/gnolang/workshops/tree/main/presentations/2024-07-09--gophercon-us--jae).

### AtomOne vs Gno.land

Gno.land (GNOT) is a separate chain from AtomOne (ATONE/PHOTON), but Gno.land
and AtomOne are complementary and symbiotic systems. While gno.land solves the
smart contract problem for all VaaS hubs, AtomOne solves the scaling problem
for all smart contract platforms. Gno.land will scale on AtomOne before any
scaling solution is proven and adopted for gno.land. Gno.land is just one of
many future smart contracting platforms, and won't be the last to scale on
AtomOne.

We don't consider programming in the Go based CosmosSDK as an alternative to
smart-contract programming for the purpose of this article because it is still
more difficult than programming a dapp in say, Gno. The amount of boilerplate
code and lines of code is much greater with the CosmosSDK, though the
performance may be better than those that run on smart contract interpreting
virtual machines. Lowering the barrier to dapp development is more impactful
when the development complexity of blockchain applications is so high. That is,
the CosmosSDK is not a smart contracting platform, but a tool for building
them.

## Utility as IBC Hub

### The N^2 IBC Problem

Gaia has many IBC connections to other chains. Many of these chains,
such as the Osmosis AMM DEX chain also have many IBC connections. Arguably all
chains that connect to many external chains via IBC is an IBC hub, we see the
current manifestation of Cosmos the IBC chain network as a precursor
step toward the desired IBC hub architecture as described in the [original
vision](https://github.com/cosmos/cosmos/blob/master/HOME.md) where there is a
distinction between hub chains and non-hub chains called zones. See also the
[2018 blog post by Gautier
Marin](https://blog.cosmos.network/understanding-the-value-proposition-of-cosmos-ecaef63350d).
We even had a newsletter called "Hub and Spoke". 

> One idea would be to connect each blockchain in the network with every other
> via a direct IBC connection. The main problem with this approach is that the
> number of connections in the network grows exponentially with the number of
> blockchains. If there are 100 blockchains in the network and each of them
> needs to maintain an IBC connection with each other, that’s 4950 connections.
> This quickly gets out of hand. - https://blog.cosmos.network/understanding-the-value-proposition-of-cosmos-ecaef63350d

Given the N-squared problem of IBC connections, it is inevitable that the
Cosmos ecosystem eventually is compelled the solve this problem. The goal of
Gaia, but perhaps moreso now AtomOne, is to present the solution before it
becomes a problem, thereby gaining adoption before other alternatives.

### Crypto Court

Besides solving the N-squared problem of efficiency, IBC hubs also offer an
important security feature which is not yet well implemented, but necessarily
will become important as a driving feature of adoption of the IBC hub-and-spoke
system. We call this ["Crypto Court"](https://github.com/jaekwon/cosmos_roadmap/tree/master/shape_of_cosmos#interchain-staking).

Crypto Court will be a judicial service offered not just for internal chains
hosted by VaaS, but also external chains connected via IBC. Crypto Court
offered two broad classes of judicial oversight as a service, whether or not
any "interchain (staking) security" is involved between the IBC hub and spoke
zone. The first class is about automatically determining determining liability
for a consensus fault, and might be called "Consensus Court".

> If there is a chain-fork, aka double-spend attack, where say two blocks get
> committed at the same height, there are enough validators (more than 1/3) to
> censor evidence from being submitted to the blockchain, so the previous
> construction doesn't work. One way to prepare blockchain failure is to delegate
> the handling of failure via a "consensus trial" on another blockchain (the
> "consensus court" zone) that was previously self-elected by that blockchain.
> Upon the discovery of Evidence that a chain has halted, represented by two
> conflicting Commits, the consensus court and validators enter into a challenge
> and response protocol to determine who is at fault for the fork of that chain.
> The protocol is described in the Tendermint wiki, but is getting formalized and
> implemented. - https://github.com/jaekwon/cosmos_roadmap/tree/master/shape_of_cosmos#interchain-staking

The second class might be called "Constitution Court", and helps enforce the
original intent of the constitution and the laws of the spoke zone even when
there is no double-signing or complex consensus fault proof, though there may
be a chain halt (but not necessarily). There is a lot of nuance that is yet to
be figured out here, but exactly how "Constitution Court" makes decisions must
be well specified in the constitution of the hub.

In both cases of Crypto Court, both Consensus Court and Constitution Court, the 
benefit of the IBC hub-and-spoke model versus the current everyone-is-a-hub model
is that failure resolution is possible.

> Say there are 10,000 zones. Say a zone fails and it requires manual
> intervention. With 10,000 IBC connections you require 10,000 zones to all agree
> on recovery procedure; will never happen. But a zone connected to a more secure
> hub will be protected when it needs intervention.
> - https://github.com/tendermint/atom_one/tree/13a717d5623e84ccb37127bb0301ae0e4bbb6999#the-need-for-hubs

### ICS/VaaS Hub Model vs IBC Hub Model

While the ICS/VaaS hub's primary business model is about scaling transaction
throughput, the IBC hub business is a natural complementary business model
(since by virtue of the many VaaS hosted shards the demand for IBC token
pegging is great).

The IBC hub model will take some time to develop, probably only fully
materializing after the VaaS feature is complete, but there are many ways to
accelerate its adoption; to be described in future articles. The main question
to be answered there, and also today for the builders of Gaia and AtomOne
hubs, is "What differentiates an IBC token hub from a zone, why is the
distinction needed, and what will get other chains and dapps to adopt the IBC
hub-and-spoke model?".

## Memecoins vs Missioncoins

So far we have described the original vision of the Cosmos and Gaia, the
utility of AtomOne and IBC hubs and ICS/VaaS hubs in general, and the primary
utility of the PHOTON token as the fee payment token for AtomOne, but there is
another element to the PHOTON fee-token to be discussed.

### Memecoins

First, let's take a look at the origin of the memecoin. The first memecoin was
created by Billy Markus and Jackson Palmer who decided to make Dogecoin as a
joke. It had no particular purpose but to have fun, and as a form of satire
about the speculative nature of Bitcoin and crypto.

### Missioncoins

There are many memecoins today, with people speculating on memecoins based on
the potential virality of the associated meme, but quite a distraction from the
original intent of Bitcoin and crypto in general. Bitcoin was created as an
alternative to traditional closed financial systems for grave existential
reasons. Ethereum was created to innovate a versatile Turing-complete
smart-contract platform. Cosmos was created to innovate classical BFT
proof-of-stake, and realize our IBC hub-and-spoke future.

With the innovation of rich smart contract programming platforms and in
particular new DAO systems and decentralized human coordination dapps, we will
see the emergence of "mission coins". The basic premise is that the tokenomics
of these missioncoins enable the funding of special purpose mission driven DAO
entities that will operate transparenty to fulfill its stated mission (or not).

Eventually, most public-goods funding will happen on chain, where the
operations of the mission driven DAO can be inspected by everyone, where
donating to the DAO is easy, and ultimately where people can easily support one
institution or the other by voting with their wallets, or more specifically by
voting with their choice of currency. Perhaps even the US dollar will give way
to various mission driven crypto tokens, regional, national and even global,
and there will be no more need to account for any taxes because it will be
integrated into the tokenomics of the chain.

## Conclusion

Staking tokens such as ATOM and ATONE as a separate class of token has utility
depending on what service the chain offers, and in the case of AtomOne the
service offered is ICS/VaaS scaling of transaction throughput. While this
narrative depends strongly on wide consumer adoption of the chain, we have
broken the problem down into three primary components (VaaS, smart contract
platform, and killer dapp) that can be worked on independently. 

So far we have been working on developing the next generation smart contract
platform with the gno.land chain and Gno VM which will first scale on AtomOne,
and we will now begin work on the core ICS/VaaS protocol work to enable the VaaS
service. AtomOne will make Cosmos great again.

## Call to Action

Visit to our [website at atom.one](https://atom.one) and sign up for our
newsletter. _A new website will be deployed on Tuesday._

Stay tuned for more updates, as we have a few things in the pipeline including
about the work beginning in ICS/VaaS, and also about one particular dapp that
we are very excited about.

AtomOne presently needs to set the Steering DAO council and BUIDL DAO council.
If you have recommendations for nominees, please contact jae@tendermint.com
with subject "[AtomOne] Council nomination" and include some detail with the
best way to reach you and the nominee. We will soon make a proposal for the
AtomOne stakers to vote on.

If you like this article, please retweet. 

-------

Special thanks to Giuseppe Natale for fixes and additional references.
