# Outline for New Developers

For the experienced developer wishing to build your own blockchain using the Komodo software, we recommend the following approach.

<aside class="notice">
  If you are not yet an experienced developer and you wish to discover an effective method to learn, we recommend coming to <a href="https://komodoplatform.com/discord">our Discord channel</a> and discussing with members of our community what steps you should take. We look forward to meeting you and seeing what you create!
</aside>

## Visit Us in Discord

First, we encourage you to come [to our Discord channel](https://komodoplatform.com/discord), and to come by frequently throughout your discovery process.

We are a deeply engaged and highly enthusiastic open-source blockchain community, always ready to get creative with like-minded people.

Ask questions in our channels such as #developer, #cryptoconditions, and others. Team and community members are usually available to assist you.

## Understand the Concept

A Komodo-based blockchain, called an "asset chain", is an independent blockchain that is forked from Komodo technology and has the option of using Komodo's many services, including Komodo's [security](#secure-this-asset-chain-with-delayed-proof-of-work) and scalability.

We use the term, "asset chain," because the coins in the blockchain are assets owned by you and your blockchain's users.

The unique combination of technology in a Komodo asset chain grants businesses and developers an increased level of freedom.

### "Why Komodo?"

There are many advantages to using the Komodo framework over other blockchain platforms.

One important thing to point out is that, at this time, a Komodo-based asset chain is unlike anything else currently available on the blockchain market.

Most other blockchain platforms run a layer-one blockchain, and the journeyman developer runs their smart-contract code in a virtual machine, or on a side chain that runs on top of the layer-one chain. In many circumstances, the end-user pays gas and transaction fees in the token of the layer-one chain, regardless of the end-user's objective.

**In Komodo, You and Your Users Get A Blockchain All To Yourself**

Komodo is completely different. You get your own full blockchain entirely to yourself. All that is required is that you keep the basic Komodo framework in place, as it facilitates your connection to [the security of the Bitcoin hash rate](#secure-this-asset-chain-with-delayed-proof-of-work), and also your connection to other blockchains in the Komodo ecosystem.

**No Gas/Transaction Fees**

Furthermore, your end-users do not have to pay gas/transaction fees in KMD for each transaction. Instead, you get to decide what is required, and we have created many tools to facilitate your approach.

**Limitless Scalability**

Even more, because your asset chain is its own independent blockchain, your scalability is limitless and is not affected by activity elsewhere in the Komodo ecosystem.

If another asset chain in the Komodo ecosystem has a sudden surge of activity, your asset chain does not slow down at all.

On the other hand, if activity on your asset chain peaks and causes your chain to slow down, you can bifurcate your asset chain into two separate asset chains that are cross-chain compatible, through our MoMoM technology. Using this method, we have already proved that the Komodo ecosystem can run more than 40,000 transactions per second, and we are prepared to scale to 1,000,000 and beyond.

In Komodo, your creativity is not limited by the mathematical constraints that affect other blockchain platforms, but instead only by hardware and your imagination.

If you want to write the first Uber-like dApp, Komodo is the platform for you.

**Your Blockchain's Engine Belongs to You**

This setup grants a competitive level of freedom to your creative endeavors.

The highly advanced developer that wishes to engineer their own consensus mechanism can move forward freely and rapidly with their ideas, backed up with the hash rate of Bitcoin.

Unlike other platforms, there is no need to wait for the Komodo team to update either the default daemon's functionality, or to update the main Komodo blockchain (KMD).

So long as we can verify and approve your changes before we pull them into our dPoW protective services, you are able to create at will.

**Discover What Others Create**

On the other hand, a casual developer that does not wish to be a core blockchain engineer, but only to build decentralized applications (dApps), also receives benefits.

When an advanced blockchain engineer in the ecosystem creates a useful new concept or template on their own asset chain, they can choose to contribute this code to the default Komodo daemon.

Once accepted by the Komodo team, this functionality is then available to all developers throughout the ecosystem.

For example, one of the asset chains in our ecosystem, VerusCoin, recently solved the Nothing-At-Stake problem that has long plagued Proof-of-Stake blockchains. They generously shared their code with the rest of the ecosystem, and it will be included in the default Komodo daemon soon.

**Many More Advantages to Discover**

These are just a few (of many!) advantages that Komodo offers to our ecosystem developers.

If you want a deep dive into how the tech works, [check out our full white paper here](https://www.komodoplatform.com/whitepaper).

### A Caveat for Daemon and Smart-Contract Developers

There is one caveat. Under most circumstances, only a highly skilled developer should make adjustments to the code that affects the internal workings of the default daemon. This caveat includes creating smart-contract templates using our technology.

For this reason, at this time our team is available to assist developers in writing smart-contract templates -- both those who wish to work outside the daemon and those who wish to work within it.

If you have an idea that you would like to make a reality on Komodo and you need assistance in writing a secure smart-contract template, please reach out to us.

We are actively working to build up our library of smart-contract templates, and will therefore do what we can to help you safely code your smart-contract idea and add it to your daemon.

This offer is only available for a limited time, and only on an "as is" basis.

Over time, as the library of secure smart-contract templates increases, it is possible that the need to create new smart-contract templates will decrease. We also hope that a community of advanced smart-contract freelance developers will grow in our ecosystem, to facilitate Komodo's adoption.

### The Cost of Running an Asset Chain

Simply creating and developing the asset chain for testing purposes does not require contact with or payment to the Komodo team.

**However, in nearly all circumstances, an asset chain is only secure once it receives our dPoW connection to the Bitcoin hash rate (dPoW).**

You can read more about how the security and payment are structured in [the section on Komodo's dPoW security services](#secure-this-asset-chain-with-delayed-proof-of-work).

In general, the cost for Komodo's security services is competitive. While the initial setup cost may or may not be higher than other blockchain platforms, the benefits that come from owning your own full blockchain, not having to pay KMD gas/transaction fees, and in being able to deploy unlimited smart contracts, can become a cost-saving advantage over time for both you and your users.

Please reach out to our team whenever you are ready to purchase dPoW. We will direct you to one of our service providers, and they can give you a direct quote for the annual cost.

<aside class="success">
  We have a limited supply of early-bird discounts. Please inquire while supply last.
</aside>

### A Brief Note About Languages

In considering the languages available in the Komodo ecosystem, there are two parts to the situation: code that runs inside your daemon, including your smart contracts; code that runs outside your daemon, including GUIs, backend databases, etc.

In both circumstances, you are able to use whatever language you desire.

However, if you are writing smart contracts or making adjustments to your daemon, we currently recommend that you have a considerable amount of programming experience, and that you work primarily in C/C++. These are the native languages of the Komodo daemon. When making adjustments to your coin's daemon, other languages can be supported, depending on the circumstances. It may incur an additional cost. Please reach out to our team with your questions.

For anything that occurs outside of the daemon, naturally you may use any language that can throw an rpc call to your coin's daemon. Most common languages support this functionality. We are working to create wrappers for importing Komodo functionality into your workflow. If you have a language that is not yet available, we welcome you to create a wrapper and contribute it to [our Github repository](https://www.github.com/komodoplatform). Please reach out to us with your language-wrapper requests.

## Install the Basic Komodo Software

So you've decide you want to take Komodo for a free test drive. Alright!

The next step is to install the software on your machine.

[Follow through the instructions here,](#installing-basic-komodo-software) and return to this spot in the outline when you are finished.

## Get Familiarized With komodod and komodo-cli

Now that you have `komodod` and `komodo-cli` installed, [skim briefly through the instructions on how to interact with a Komodo-based daemon, linked here](#interacting-with-komodo-chains).

You'll come back to this section later, once you're ready to execute rpc calls, API commands, and runtime parameters.

<aside class="notice">
  You do not need to launch or sync the main Komodo chain (KMD), and you do not need to own any KMD to test an asset chain.
</aside>

## Create Your First Asset Chain

With `komodod` and `komodo-cli` installed you're ready to spin up an asset chain.

[Follow the instructions in this linked guide to build your first asset chain.](#creating-a-new-asset-chain)

We recommend that you use the simplest of settings when creating your first chain.

For example:

`./komodod -ac_name=HELLOWORLD -ac_supply=777777 &`

## Execute Elementary RPC Calls
After you have your asset chain running on both nodes, we recommend executing some basic rpc calls in the terminal.

Here are links to some simple and common rpc examples:

[`getnewaddress`](#getnewaddress)

[`sendtoaddress`](#sendtoaddress)

[`getinfo`](#getinfo)

As Komodo is downstream from both Bitcoin and Zcash, essentially all of the commands that are available on those two upstream blockchains are also available here.

## Test Out Platform-Specific Features

We create many features, functionalities, and commands that are specifically designed for dApp and platform-oriented developers.

For example, you can learn how to make asset chains that are more complicated in nature.

[Read this documentation first to get the basic idea](#asset-chain-parameters).

Once you understand the concept, you can add in asset-chain tricks -- like making your asset chain's consensus mechanism [a mix between Proof of Work and Proof of Stake](#ac_staked).

Or, you could make your asset chain suitable for a rapid mining period, followed by complete blockchain disposal. Use parameters such as [`ac_end`](#ac_end), [`ac_reward`](#ac_reward), [`ac_decay`], and [`ac_perc`](#ac_perc) for this effect.

## Discover CC Smart Contracts

Now you should be ready to head into smart contract territory.

First, you must create an asset chain that has the [ac_cc runtime parameter properly enabled](#ac_cc).

**===Documentation for the following examples is not yet imported, coming very soon===**

With this activated, you can try a few existing templates.

You can [create ERC20 tokens on your new asset chain](#tokens), try using your [built-in on-chain DEX](#trade), use [the DICE smart-contract template](#dice) to do some blockchain-enforced gambling, and more.

## Write Your Own Smart Contracts

If you're ready to try out your own customized smart contract, please read the detailed technical documentation written by our lead developer, JL777: [Mastering CryptoConditions](https://github.com/jl777/komodo/blob/FSM/src/cc/CC%20made%20easy).

## Learn About BarterDEX and Agama

Once you purchase our[ dPoW security services and scalability solutions](#secure-this-asset-chain-with-delayed-proof-of-work), you are eligible to add your asset chain to our ecosystem-wide native DEX, [BarterDEX](#komodo-39-s-native-dex-barterdex), and our multi-coin wallet, Agama.

You can learn more about both on [docs.komodoplatform.com](https://docs.komodoplatform.com), and we should import some of that documentation here soon.

## Visit Us in Discord

Once again, we remind you to come visit us in [our Discord channel](https://komodoplatform.com/discord)!

We appreciate your interest, and hope to give you a pleasant developer experience.
