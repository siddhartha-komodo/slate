# Introduction

Welcome to the Komodo API Reference Guide.

Komodo's blockchain technology enables developers to run fully independent blockchains in a secure and highly competitive environment.

Each independent blockchain built on the Komodo framework has a wide range of capabilities, including Bitcoin-hash rate supported security, zero-knowledge privacy, enterprise-level scalability, consensus-level smart contracts, cross-chain interoperability, and more. Because a Komodo-based blockchain is independently managed, the developer has complete freedom, so long as the essential connections to the Komodo ecosystem remain.

If you find any bugs or if you have any questions, please reach out by [submitting a ticket](https://support.komodoplatform.com/support/home), or by speaking to us directly on [our Discord channel](https://komodoplatform.com/discord).

## Installing Basic Komodo Software

To install the Komodo daemon, `komodod`, and its necessary counterpart, `komodo-cli`, the simplest method is to [download and install a packaged version](https://github.com/KomodoPlatform/komodo/releases).

Once installed, you should find `komodod` and `komodo-cli` in the following directory structure:

`LOCATION_OF_AGAMA_INSTALLATION/komodo/src/`

You may also build `komodod` and `komodo-cli` from source, when you are ready to keep abreast of the latest features and updates. This is not necessary during the testing phase, but is considered the best practice for a blockchain in a production setting. Building from source enables you to receive security patches the moment they are pushed to the `komodod` source.

You will find [a walkthrough on building from source here](https://docs.komodoplatform.com/komodo/install-Komodo-manually.html).

## Interacting with Komodo Chains

There are two cooperating pieces of software that the user utilizes when running a Komodo-compatible blockchain from the command line.

The first is the coin daemon itself, `komodod`. This is initiated by calling it from the command line and including any desired runtime parameters. When initiating any Komodo-compatible blockchain other than the main KMD blockchain, the user should also include the `-ac_name=COINNAME` and `-ac_supply=COINSUPPLY` parameters.

Once [the `komodod` software is installed](https://github.com/KomodoPlatform/komodo/releases), find the location you chose to install it, and `cd` into the `/komodod/src` subdirectory. There, you should see `komodod` and `komodo-cli`.

<aside class="notice">
  If you are using windows, replace `./komodod` and `./komodo-cli` with `komodod.exe` and `komodo-cli.exe` for each step.
</aside>

To launch the main KMD chain, execute:

`./komodod`

After the daemon launches, you may interact with it using `komodo-cli` like so:

`./komodo-cli API_COMMAND`

To launch another Komodo-based blockchain, include the necessary parameters. The list of launch parameters for each Komodod-based blockchain [is found here](https://github.com/VerusCoin/VerusCoin/blob/master/src/assetchains.old).

For example, to launch the DEX asset chain, execute:

`./komodod -pubkey=$pubkey -ac_name=DEX -ac_supply=999999 -addnode=78.47.196.146 $1 &`

<aside class="notice">
  IMPORTANT: Always execute the launch command EXACTLY as indicated, and as the asset-chain's developers instruct. Failure to do so will cause the blockchain's internal settings to malfunction, and you will have to reinstall and re-sync to regain access to the blockchain's network.
</aside>

To interact with the DEX daemon, use `komodo-cli` like so:

`./komodo-cli -ac_name=DEX API_COMMAND`

Detailed descriptions of all Komodo commands and parameters are provided below.

Also, in the terminal you can call the Komodo documentation by executing:

`komodo-cli help`

To learn more via the terminal about a specific API command, execute:

`komodo-cli help API_COMMAND`

For more information about creating and interacting with asset chains, please visit our [asset-chain creation documentation](#komodo-asset-chain-basics).

Follow this link to find information on [accessing the coin daemon remotely](#accessing-the-coin-daemon-remotely).

<aside class="warning">
  IMPORTANT: In nearly all circumstances, any blockchain you build should NOT be considered secure until it receives the dPoW security service.
</aside>

## Komodo's Native DEX: BarterDEX

Komodo offers built-in native decentralized-exchange (DEX) compatibility through our software, BarterDEX. This software is separate from `komodod` and `komodo-cli`.

BarterDEX is a pioneer in atomic-swap based exchange methods, and via our open-source philosophy, anyone is welcome to use it without restriction. Through our atomic-swap technology the end-users utilizing BarterDEX maintain ownership of their private keys at all times. Therefore, the developers maintaining any cluster of traders utilizing the BarterDEX software are not acting in the capacity of escrow-service and trading providers, unlike other exchanges.

Because the BarterDEX software is separate from `komodod` and `komodo-cli`, at this time we do not include it in this API documentation. Rather, you may find [API documentation for BarterDEX here](https://docs.komodoplatform.com/barterDEX/barterDEX-API.html).
