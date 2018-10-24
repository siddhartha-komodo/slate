# Introduction

Welcome to the Komodo API Reference Guide.

Komodo's blockchain technology enables developers to run fully independent blockchains in a secure and highly competitive environment.

Each independent blockchain built on the Komodo framework has a wide range of capabilities, including Bitcoin-hash rate supported security, zero-knowledge privacy, enterprise-level scalability, consensus-level smart contracts, cross-chain interoperability, and more. Because a Komodo-based blockchain is independently managed, the developer has complete freedom, so long as the essential connections to the Komodo ecosystem remain.

If you find any bugs or if you have any questions, please reach out by [submitting a ticket](https://support.komodoplatform.com/support/home), or by speaking to us directly on [our Discord channel](https://komodoplatform.com/discord).

## Installing Basic Komodo Software

To install the Komodo daemon, `komodod`, and its necessary counterpart, `komodo-cli`, the simplest method is to [install the latest version of the Agama wallet](https://komodoplatform.com/komodo-wallets/). Follow the instructions for your preferred operating system.

Once installed, you should find `komodod` and `komodo-cli` in the following directory structure:

`LOCATION_OF_AGAMA_INSTALLATION/resources/app/assets/bin/OS_NAME/`

You may also build `komodod` and `komodo-cli` from source, when you are ready to keep abreast of the latest features and updates. This is not necessary during the testing phase, but is considered the best practice for a blockchain in a production setting. Building from source enables you to receive security patches the moment they are pushed to the `komodod` source.

You will find [a walkthrough on building from source here](https://docs.komodoplatform.com/komodo/install-Komodo-manually.html).

## Interacting with Komodo Chains

There are two cooperating pieces of software that the user utilizes when running a Komodo-compatible blockchain from the command line.

The first is the coin daemon itself, `komodod`. This is initiated by calling it from the command line and including any desired runtime parameters. When initiating any Komodo-compatible blockchain other than the main KMD blockchain, the user should also include the `-ac_name=COINNAME` and `-ac_supply=COINSUPPLY` parameters.

Once installed, find the installation location.

* Binary:
https://github.com/KomodoPlatform/komodo/releases

If you used the default Agama installer:

MacOS: `?`

Windows: `?`

GNU/Linux: `/opt/AgamaApp/resources/app/assets/bin/OS_NAME/`

If you built Komodo from source:

MacOS: `?`

Win: `?`

GNU/Linux: `~/komodo/src/`

To launch the main KMD chain, execute:

`./komodod`

After the daemon launches, you may interact with it using `komodo-cli` like so:

`./komodo-cli [API Command]`

If you are using windows, replace `./komodod` and `./komodo-cli` with `komodod.exe` and `komodo-cli.exe` for each step.

To launch another Komodo-based blockchain, include the necessary parameters. The list of launch parameters for each Komodod-based blockchain [is found here](https://github.com/VerusCoin/VerusCoin/blob/master/src/assetchains.old).

For example, to launch the DEX asset chain, execute:

`./komodod -pubkey=$pubkey -ac_name=DEX -ac_supply=999999 -addnode=78.47.196.146 $1 &`

<aside class="notice">
IMPORTANT: Always execute the launch command EXACTLY as indicated, and as the asset-chain's developers instruct. Failure to do so will cause the blockchain's internal settings to malfunction, and you will have to reinstall and re-sync to regain access to the blockchain's network.
</aside>

To interact with the DEX daemon, use `komodo-cli` like so:

`./komodo-cli -ac_name=DEX getnewaddress`

Detailed descriptions of all Komodo commands and parameters are provided below.

Also, in the terminal you can call the Komodo documentation by executing:

`komodo-cli help`

To learn more via the terminal about a specific API command, execute:

`komodo-cli help [API COMMAND]`

For more information about creating and interacting with asset chains, please visit our [full asset-chain creation documentation here](https://docs.komodoplatform.com/komodo/create-Komodo-Assetchain.html).

Follow this link to find information on [accessing the coin daemon remotely](## Accessing the Coin Daemon Remotely).

<aside class="warning">
IMPORTANT: In nearly all circumstances, any blockchain you build should NOT be considered secure until it receives our dPoW security services.
</aside>

## Komodo's Native DEX: BarterDEX

Komodo offers built-in compatibility with a our separately created, atomic-swap powered, decentralized-exchange engine, BarterDEX.

Through the atomic-swap technology that we pioneer, anyone can use our decentralized software, and the end-users utilizing BarterDEX maintain ownership of their private keys at all times. This means that the developers maintaining any cluster of traders utilizing the BarterDEX software are not acting in the capacity of escrow-service and trading providers, unlike other exchanges.

BarterDEX's software is installed and accessed separately.

Because the BarterDEX software is separate from `komodod` and `komodo-cli`, at this time we do not include it in this API documentation. Rather, you may find [API documentation for BarterDEX here](https://docs.komodoplatform.com/barterDEX/barterDEX-API.html).
