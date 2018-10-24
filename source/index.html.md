---
title: Komodo API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - shell
  - python
  - javascript

toc_footers:
  - <a href='https://www.komodoplatform.com'>Komodo Website</a>
  - <a href='https://github.com/lord/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true
---

# Introduction

Welcome to the Komodo API Reference Guide.

Komodo's blockchain technology enables developers to run fully independent blockchains in a secure and highly competitive environment.

Each independent blockchain built on the Komodo framework has a wide range of capabilities, including Bitcoin-hash rate supported security, zero-knowledge privacy, enterprise-level scalability, consensus-level smart contracts, cross-chain interoperability, and more. Because a Komodo-based blockchain is independently managed, the developer has complete freedom, so long as the essential connections to the Komodo ecosystem remain.

If you find any bugs or if you have any questions, please reach out by [submitting a ticket](https://support.komodoplatform.com/support/home), or by speaking to us directly on [our Discord channel](https://komodoplatform.com/discord).

## Installing Basic Komodo Software

To install the Komodo daemon, `komodod`, and its necessary counterpart, `komodo-cli`, the simplest method is to [install the latest version of the Agama wallet](https://komodoplatform.com/komodo-wallets/). Follow the instructions for your preferred operating system.

Once installed, you should find `komodod` and `komodo-cli` in the following directory structure:

`LOCATION_OF_AGAMA_INSTALLATION/resources/app/assets/bin/OS_NAME/`

You may also build `komodod` and `komodo-cli` from source, when you are ready to keep abreast of the latest features and updates. This is not necessary during the testing phase, but is considered the best practice for a blockchain in a production setting. Building from source enables you to receive security patches the moment they are pushed to the `komodod` source. You may find [a walkthrough here](https://docs.komodoplatform.com/komodo/install-Komodo-manually.html).

## Interacting with Komodo-based Blockchains

Navigate to this location, and then to launch the main KMD chain, execute:

`./komodod`

After the daemon launches, you may interact with it using `komodo-cli` like so:

`./komodo-cli getnewaddress`

Likewise, the `komodod` daemon allows you to launch other Komodo-based blockchains, and `komodo-cli` allows you to interact. The list of launch parameters [for each Komodod-based blockchain can be found here](https://github.com/VerusCoin/VerusCoin/blob/master/src/assetchains.old).

For example, to launch the DEX asset chain, execute:

`./komodod -pubkey=$pubkey -ac_name=DEX -ac_supply=999999 -addnode=78.47.196.146 $1 &`

<aside class="warning">
IMPORTANT: Always execute the launch command EXACTLY as it appears in this list, or as the asset-chain's developers instruct. Failure to do so will cause the 'magic' property to malfunction, and you will have to reinstall and re-sync to regain access to the blockchain's network.
</aside>

To interact with the DEX daemon, use `komodo-cli` like so:

`./komodo-cli -ac_name=DEX getnewaddress`

Detailed descriptions of all Komodo commands and parameters are provided below.

For more information about creating and interacting with asset chains, please visit our [full documentation here](https://docs.komodoplatform.com/komodo/create-Komodo-Assetchain.html).

<aside class="warning">
IMPORTANT: In nearly all circumstances, any blockchain you build should NOT be considered secure until it receives our dPoW security services.
</aside>

For more details on launching your own Komodo-based blockchain, please read [this walkthrough](https://docs.komodoplatform.com/komodo/create-Komodo-Assetchain.html).


We have language bindings in Shell, Ruby, Python, and JavaScript! You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.

### Sub-Sub-Introduction

This example API documentation page was created with [Slate](https://github.com/lord/slate). Feel free to edit it and use it as a base for your own API's documentation.

## Installing DEX Softare

> To authorize, use this code:

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
```

```shell
# With shell, you can just pass the correct header with each request
curl "api_endpoint_here"
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
```

> Make sure to replace `meowmeowmeow` with your API key.

Kittn uses API keys to allow access to the API. You can register a new Kittn API key at our [developer portal](http://example.com/developers).

Kittn expects for the API key to be included in all API requests to the server in a header that looks like the following:

`Authorization: meowmeowmeow`

<aside class="notice">
You must replace <code>meowmeowmeow</code> with your personal API key.
</aside>

# Kittens

## Get All Kittens

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.get()
```

```shell
curl "http://example.com/api/kittens"
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let kittens = api.kittens.get();
```

> The above command returns JSON structured like this:

```json
[
  {
    "id": 1,
    "name": "Fluffums",
    "breed": "calico",
    "fluffiness": 6,
    "cuteness": 7
  },
  {
    "id": 2,
    "name": "Max",
    "breed": "unknown",
    "fluffiness": 5,
    "cuteness": 10
  }
]
```

This endpoint retrieves all kittens.

### HTTP Request

`GET http://example.com/api/kittens`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
include_cats | false | If set to true, the result will also include cats.
available | true | If set to false, the result will include kittens that have already been adopted.

<aside class="success">
Remember — a happy kitten is an authenticated kitten!
</aside>

## Get a Specific Kitten

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.get(2)
```

```shell
curl "http://example.com/api/kittens/2"
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.get(2);
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "name": "Max",
  "breed": "unknown",
  "fluffiness": 5,
  "cuteness": 10
}
```

This endpoint retrieves a specific kitten.

<aside class="warning">Inside HTML code blocks like this one, you can't use Markdown, so use <code>&lt;code&gt;</code> blocks to denote code.</aside>

### HTTP Request

`GET http://example.com/kittens/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the kitten to retrieve

## Delete a Specific Kitten

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.delete(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.delete(2)
```

```shell
curl "http://example.com/api/kittens/2"
  -X DELETE
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.delete(2);
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "deleted" : ":("
}
```

This endpoint deletes a specific kitten.

### HTTP Request

`DELETE http://example.com/kittens/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the kitten to delete
