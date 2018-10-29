# Asset Chain Parameters

The Komodo platform offers various default customizations for determining the underlying nature of your asset chain. The desired combination of parameters should be included with the `komodod` execution every time the asset-chain daemon is launched.

Changing these customizations at a later time is possible, but in many circumstances it can require a hard fork of your asset chain. In general, it is best to have your asset chain's parameters finalized before decentralizing the ownership of your coin. Should you discover a need to change these parameters after the fact, please reach out to our development team for assistance.

## -ac_name

This is the ticker symbol for the coin you wish to create. We recommended it consist only of numbers and uppercase letters.

All asset chains are required to set `-ac_name`.

-ac_supply
==========

This is the amount of pre-mined coins you would like the chain to have.

The node that sets `-gen` during the creation process will mine these coins in the genesis block.

If `-ac_supply` is not set, `-ac_reward` must be set, and a default value of 10 coins will be used in the genesis block. If `-ac_pubkey` is set, the  pre-mined coins will be mined to the address of the corresponding pubkey.

The `-ac_supply` parameter should be set to a whole number without any decimals places. It should also be to set to less than `2000000000` to avoid 64-bit overflows.

Note: An additional fraction of a coin will be added to this based on the asset chain's parameters. This is used by nodes to verify the genesis block. For example, the DEX chain's `-ac_supply` parameter is set to `999999`, but in reality the genesis block was `999999.13521376`.

All chains are required to set `-ac_supply`.

-ac_reward
==========
This is the block reward for each mined block, given in satoshis. If this is not set, the block reward will be `10000` satoshis, and blocks will be on-demand after block 127 (a new block will not be mined unless there is a transaction in the mempool.)

-ac_end
=======
This is the block height in which block rewards will end. Every block after this height will have 0 block reward.

-ac_halving
===========
This is the number of blocks between each block reward halving. This parameter will have no effect if `-ac_reward` is not set. The lowest possible value is `1440` (~1 day). If this parameter is set, but `-ac_decay` is not, the reward will decrease by 50% each halving.

-ac_decay
=========

This is the percentage the block reward will decrease by each block-reward halving. This parameter will have no effect if `-ac_reward` is not set.

This is the formula that `-ac_decay` follows:

.. code-block:: shell

	numhalvings = (height / -ac_halving);
	for (i=0; i<numhalvings; i++)
	reward_after = reward_before * ac_decay / 100000000;

For example, if this is set to `750000000`, the block reward will drop 25% from the previous block reward each halving.

-ac_perc
========

The `-ac_perc` parameter is the percentage added to both the block reward and to the transactions that will be sent to the ===link=== `-ac_pubkey` address. If the `-ac_perc` parameter is set, `-ac_pubkey` must also be set.

For example, if `-ac_reward=100000000` and `-ac_perc=10000000`, for each block mined, the miner receives 1 coin along with the `-ac_pubkey` address receiving 0.1 coin. For every transaction sent, the pubkey address will receive 10% of the overall transaction value. This 10% is not taken from the user, rather it is created at this point. Each transaction inflates the overall supply.

	Note: Vout 1 of each coinbase transaction must be the correct amount sent to the corresponding `pubkey`. The `vout` type for all coinbase vouts must be `pubkey` as opposed to `pubkeyhash`. This only affects a miner trying to use a stratum. Z-nomp is currently incompatible.

-ac_pubkey
==========

The `-ac_pubkey` parameter designates a public address for receiving payments from the network. These payments can come in the genesis block, in all blocks mined thereafter, and from every transaction on the network.

It is used in combination with ===link=== `-ac_perc`, which sets the amount that is sent to the address. If `ac_perc` is not set, the only effect of `ac_pubkey` is to have the genesis block be mined to the `pubkey` specified.

If `-ac_pubkey` is set, but ===link=== `-ac_perc` is not, this simply means the genesis block will be mined to the set `pubkey`'s address, and no blocks or transactions thereafter will mine payments into the `pubkey`.

`pubkey` must be set to a 33 byte hex string. You can get the pubkey of an address by using the ===link=== `validateaddress` command in `komodod`, and searching for the returned `pubkey` property. The address must be imported to the wallet before using `validateaddress`.

-ac_cc
======

 * **NOTE:** This parameter is still in testing.

The `-ac_cc` parameter sets the network cluster on which the chain can interact with other chains via ===link=== cross-chain smart contracts and ===link=== MoMoM technology.

Under most circumstances, this parameter requires the Komodo notarization service to achieve functionality, as it relies on the `pubkey` of the trusted notary nodes to ensure coin-supply stability.

Once activated, the `ac_cc` parameter can allow features such as cross-chain fungibility -- meaning that coins on one asset chain can be directly transferred to another asset chain that has the same `ac_cc` setting and notary nodes with the same `pubkey`.

-ac_cc=0
--------

Setting `-ac_cc=0` disables smart contracts on the asset chain entirely.

-ac_cc=1
--------

Setting `-ac_cc=1` permits smart contracts on the asset chain, but will not allow the asset chain to interact in cross-chain smart contracts with other asset chains.

-ac_cc=2 to 100
---------------

The values of `2` through `100` indicate asset chains that can import functions across asset chains, but their coins are not fungible.

For example, an asset chain may be able to query another asset chain on the same `ac_cc` cluster for details about a transaction.

However, coins may not be transferred between blockchains.

-ac_cc=101 to 9999
------------------

Setting the value of `ac_cc` to any value greater than or equal to `101` will permit cross-chain interaction with any asset chain that has the same `ac_cc` value and is secured by notary nodes with the same `pubkey`. For example, an asset chain set to `ac_cc=2` in its parameters can interact with other asset chains with `ac_cc=2`, on the same notary-node network, but cannot interact with an asset chain set to `ac_cc=3`.

-ac_staked
==========

.. note::

	This feature is currently only available in the `jl777 branch <https://github.com/jl777/komodo/tree/jl777>`_.

This is the percentage of blocks the chain will aim to have mined via Proof of Stake (PoS), with the remainder via Proof of Work (PoW). For example, an `ac_staked=90` chain will have ~90% PoS blocks/10% PoW blocks. Measurements of the PoS:PoW ratio are approximate; the PoW difficulty will automatically adjust based on the overall percentage of PoW-mined blocks to adhere to the approximate `PoS` value.

Each staked block will have an additional transaction added to the coinbase in which the coins that staked the block are sent back to the same address. This is used to verify which coins staked the block, and this allows for compatibility with existing Komodo infrastructure. If `-ac_staked` is used in conjunction with `-ac_perc`, the `-ac_pubkey` address will receive slightly more coins for each staked block compared to a mined block because of this extra transaction.

The following are the (current) rules for staking a block:

	#. Block timestamps are used as the monotonically increasing timestamp. It is important to have a synced system clock.

	#. In order to stake, you must use `-gen -genproclimit=0` while launching the daemon or `komodo-cli -ac_name=<CHAINNAME> setgenerate true 0` after launching the daemon.

	#. A utxo is not eligible without `nLockTime` set and until 6000 seconds has passed from this lock time. `(100 * expected blocktimes) to be exact`

	#. There are 64 different segments(`segids`) of addresses, based on the hash of the destination address. `((nHeight + addrhash.uints[0]) & 0x3f)` The segid of an address can be found with the `validateaddress` command. Each segid will take turns being segid0 at each height. `(height % 64) = the segid0 for that height.` All other segid will adjust the elapsed time by `segid` seconds.

	#. A new block is eligible to be staked 2 seconds after median blocktime. For example, segid0 for a given height will be eligible to submit a block 2 seconds after median blocktime, whereas segid1 will be eligible to submit a block 4 seconds after median blocktime. For the next block, segid0 from the previous block will now be segid63 and will be eligible to submit a block 128 seconds after median blocktime. This means by 128 seconds after the median blocktime, all segids are eligible.

	#. Coinage calculated from the adjusted time is used to divide hash(address + pastblockhash) to create the value compared against the difficulty to determine if a block is won or not. This means a UTXO is more likely to win a block within a segid based on age of the UTXO and amount of coins.

To create a chain using this parameter, start the first node with `-gen -genproclimit=0`. Start the second node with `-gen -genproclimit=$(nproc)`. Send coins from the second node to the first node, and it will begin staking. The first 100 blocks will allow PoW regardless of the `ac_staked` value.

	Note: On a chain using a high percentage for PoS, it's vital to have coins staking by block 100.  If too many PoW blocks are mined consecutively at the start of the chain, the PoW difficulty may increase enough to stop the chain entirely. This can prevent users from sending transactions to staking nodes.

	Note: It is also vital to stake coins in all 64 segids. For the time being, you can use the `genaddresses.py` script in `this repo <https://github.com/alrighttt/dockersegid>`_ to generate an address for each segid. This functionality will soon be integrated directly into the daemon. You can use the `getbalance64` command to get the balance you currently have in each segid you are staking in.

-ac_public
==========

.. note::
	This feature is currently only available in the `jl777 branch <https://github.com/jl777/komodo/tree/jl777>`_.

If `ac_public` is set to `1`, zk-SNARKs are disabled, and all z address functionalilty is disabled. Therefore, all transactions on the blockchain are public.

-ac_private
===========

.. note::
	This feature is currently only available in the `jl777 branch <https://github.com/jl777/komodo/tree/jl777>`_.

If `ac_private` is set to `1`, all transactions other than coinbase transactions (block rewards) must use zk-SNARKs. All transparent address functionality other than sending mined coins from transparent addresses is disabled.

Please send any critiques or feedback to Alright or gcharang on matrix or discord.

`Discord Invite <https://discord.gg/SCdf4eh>`_
