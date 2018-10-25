# Blockchain

The following RPC calls interact with the `komodod` software, and are made available through the `komodo-cli` software.

## getbestblockhash

```
  command:

  komodo-cli getbestblockhash

  response:

  0dd66ee1f151c38f73843378c08715ee3f4d3cf2888783e2846b81c057987084
```

> You can find your rpcusername, rpcpassword, and rpcport in the coin's .conf file.

```
  command:

  curl --user myrpcuser:myrpcpassword --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "getbestblockhash", "params": [] }' -H 'content-type: text/plain;' http://127.0.0.1:myrpcport/

  response:

  {
    "result": "0dd66ee1f151c38f73843378c08715ee3f4d3cf2888783e2846b81c057987084",
    "error": null,
    "id": "curltest"
  }
```

**getbestblockhash**

The `getbestblockhash` method returns the hash of the best (tip) block in the longest block chain.

### Arguments:

Structure|Type|Description
---------|----|-----------
(none) | |

### Response:

Structure|Type|Description
---------|----|-----------
"hex"|(string)|the block hash, hex encoded

## getblock

```
command:

komodo-cli getblock "00000000c937983704a73af28acdec37b049d214adbda81d7e2a3dd146f6ed09"

response:

{
  "hash": "0dd66ee1f151c38f73843378c08715ee3f4d3cf2888783e2846b81c057987084",
  "confirmations": 1,
  "size": 278,
  "height": 398,
  "version": 4,
  "merkleroot": "d6e8292d85181a177c21497a7e636fc4f1eef1fbd2887b3a19e1d72134429668",
  "segid": -2,
  "tx": [
    "d6e8292d85181a177c21497a7e636fc4f1eef1fbd2887b3a19e1d72134429668"
  ],
  "time": 1536603968,
  "nonce": "00002474e66d5ef243d7b0a8eec32983492daf29e0b0887bd67b2107d1000004",
  "solution": "30a5e9153392b643d139cf205b270d55cb7d3b4779fd7a3666bdb744ef221c966fde1324",
  "bits": "200f0ef8",
  "difficulty": 1.000023305960651,
  "chainwork": "0000000000000000000000000000000000000000000000000000000000001a7f",
  "anchor": "59d2cde5e65c1414c32ba54f0fe4bdb3d67618125286e6a191317917c812c6d7",
  "valuePools": [
    {
      "id": "sprout",
      "monitored": true,
      "chainValue": 0.00000000,
      "chainValueZat": 0,
      "valueDelta": 0.00000000,
      "valueDeltaZat": 0
    }
  ],
  "previousblockhash": "09f9b547842b38a7748c8633eedb609b269138fdb3f2f75570fcb0d653fe42f4"
}
```

```
command:

komodo-cli getblock "0dd66ee1f151c38f73843378c08715ee3f4d3cf2888783e2846b81c057987084" false

response:

04000000f442fe53d6b0fc7055f7f2b3fd3891269b60dbee33868c74a7382b8447b5f9096896423421d7e1193a7b88d2fbf1eef1c46f637e7a49217c171a18852d29e8d6000000000000000000000000000000000000000000000000000000000000000040b7965bf80e0f20040000d107217bd67b88b0e029af2d498329c3eea8b0d743f25e6de6742400002430a5e9153392b643d139cf205b270d55cb7d3b4779fd7a3666bdb744ef221c966fde13240101000000010000000000000000000000000000000000000000000000000000000000000000ffffffff05028e010101ffffffff0110270000000000002321033097c6f4b12bd13a2e39b686b3a2fc30fe55a1d51221d857421e40564d5e237cac3fb7965b
```

> You can find your rpcusername, rpcpassword, and rpcport in the coin's .conf file.

```
command:

curl --user myrpcuser:myrpcpassword --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "getblock", "params": ["00000000c937983704a73af28acdec37b049d214adbda81d7e2a3dd146f6ed09"] }' -H 'content-type: text/plain;' http://127.0.0.1:myrpcport/

response:

{
  "result": {
    "hash": "0dd66ee1f151c38f73843378c08715ee3f4d3cf2888783e2846b81c057987084",
    "confirmations": 1,
    "size": 278,
    "height": 398,
    "version": 4,
    "merkleroot": "d6e8292d85181a177c21497a7e636fc4f1eef1fbd2887b3a19e1d72134429668",
    "segid": -2,
    "tx": [
      "d6e8292d85181a177c21497a7e636fc4f1eef1fbd2887b3a19e1d72134429668"
    ],
    "time": 1536603968,
    "nonce": "00002474e66d5ef243d7b0a8eec32983492daf29e0b0887bd67b2107d1000004",
    "solution": "30a5e9153392b643d139cf205b270d55cb7d3b4779fd7a3666bdb744ef221c966fde1324",
    "bits": "200f0ef8",
    "difficulty": 1.000023305960651,
    "chainwork": "0000000000000000000000000000000000000000000000000000000000001a7f",
    "anchor": "59d2cde5e65c1414c32ba54f0fe4bdb3d67618125286e6a191317917c812c6d7",
    "valuePools": [
      {
        "id": "sprout",
        "monitored": true,
        "chainValue": 0,
        "chainValueZat": 0,
        "valueDelta": 0,
        "valueDeltaZat": 0
      }
    ],
    "previousblockhash": "09f9b547842b38a7748c8633eedb609b269138fdb3f2f75570fcb0d653fe42f4"
  },
  "error": null,
  "id": "curltest"
}
```

> You can find your rpcusername, rpcpassword, and rpcport in the coin's .conf file.

```
command:

curl --user myrpcuser:myrpcpassword --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "getblock", "params": ["00000000c937983704a73af28acdec37b049d214adbda81d7e2a3dd146f6ed09", false] }' -H 'content-type: text/plain;' http://127.0.0.1:myrpcport/

response:

{
  "result": "04000000f442fe53d6b0fc7055f7f2b3fd3891269b60dbee33868c74a7382b8447b5f9096896423421d7e1193a7b88d2fbf1eef1c46f637e7a49217c171a18852d29e8d6000000000000000000000000000000000000000000000000000000000000000040b7965bf80e0f20040000d107217bd67b88b0e029af2d498329c3eea8b0d743f25e6de6742400002430a5e9153392b643d139cf205b270d55cb7d3b4779fd7a3666bdb744ef221c966fde13240101000000010000000000000000000000000000000000000000000000000000000000000000ffffffff05028e010101ffffffff0110270000000000002321033097c6f4b12bd13a2e39b686b3a2fc30fe55a1d51221d857421e40564d5e237cac3fb7965b",
  "error": null,
  "id": "curltest"
}
```

```
command:

komodo-cli getblock 120

response:

{
  "hash": "0939408360b273fd681bbe5823999655fd5a7240303cdcbf952afe252246cc13",
  "confirmations": 279,
  "size": 277,
  "height": 120,
  "version": 4,
  "merkleroot": "4781cefbf7e14f6d7cdf89ae972391ae59b5776d1ed51204e94e65adf3ca6331",
  "segid": -2,
  "tx": [
    "4781cefbf7e14f6d7cdf89ae972391ae59b5776d1ed51204e94e65adf3ca6331"
  ],
  "time": 1536347890,
  "nonce": "000054c5822bb572319a67a89a3f511cf8caf8cd8ed6b7739c0b044b62ea000b",
  "solution": "03fc1abba5f415b1c422942835d46c7ba3e94665964da4c31e236c6cf9b3dfe6ffb65db1",
  "bits": "200f0f08",
  "difficulty": 1.000007093003461,
  "chainwork": "0000000000000000000000000000000000000000000000000000000000000809",
  "anchor": "59d2cde5e65c1414c32ba54f0fe4bdb3d67618125286e6a191317917c812c6d7",
  "valuePools": [
    {
      "id": "sprout",
      "monitored": true,
      "chainValue": 0.00000000,
      "chainValueZat": 0,
      "valueDelta": 0.00000000,
      "valueDeltaZat": 0
    }
  ],
  "previousblockhash": "01d1bfef50e079c53b36463fdf0ae55dc26b2205cd5f39c2bd030d19c2375e28",
  "nextblockhash": "0438bfda6a2706a622df7808fa5f4f32ac2e5d3039895ff8cb080d7e8e231188"
}
```

```
command:

komodo-cli getblock 120 false

response:

04000000285e37c2190d03bdc2395fcd05226bc25de50adf3f46363bc579e050efbfd1013163caf3ad654ee90412d51e6d77b559ae912397ae89df7c6d4fe1f7fbce81470000000000000000000000000000000000000000000000000000000000000000f2ce925b080f0f200b00ea624b040b9c73b7d68ecdf8caf81c513f9aa8679a3172b52b82c55400002403fc1abba5f415b1c422942835d46c7ba3e94665964da4c31e236c6cf9b3dfe6ffb65db10101000000010000000000000000000000000000000000000000000000000000000000000000ffffffff0401780101ffffffff011027000000000000232103c0259e1a166e53f6ccf094ce37c0843d4a013622603bc301b4eb0f89c7cce823acf1ce925b
```

> You can find your rpcusername, rpcpassword, and rpcport in the coin's .conf file.

```
command:

curl --user myrpcuser:myrpcpassword --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "getblock", "params": ["120"] }' -H 'content-type: text/plain;' http://127.0.0.1:myrpcport/

response:

{
  "result": {
    "hash": "0939408360b273fd681bbe5823999655fd5a7240303cdcbf952afe252246cc13",
    "confirmations": 279,
    "size": 277,
    "height": 120,
    "version": 4,
    "merkleroot": "4781cefbf7e14f6d7cdf89ae972391ae59b5776d1ed51204e94e65adf3ca6331",
    "segid": -2,
    "tx": [
      "4781cefbf7e14f6d7cdf89ae972391ae59b5776d1ed51204e94e65adf3ca6331"
    ],
    "time": 1536347890,
    "nonce": "000054c5822bb572319a67a89a3f511cf8caf8cd8ed6b7739c0b044b62ea000b",
    "solution": "03fc1abba5f415b1c422942835d46c7ba3e94665964da4c31e236c6cf9b3dfe6ffb65db1",
    "bits": "200f0f08",
    "difficulty": 1.000007093003461,
    "chainwork": "0000000000000000000000000000000000000000000000000000000000000809",
    "anchor": "59d2cde5e65c1414c32ba54f0fe4bdb3d67618125286e6a191317917c812c6d7",
    "valuePools": [
      {
        "id": "sprout",
        "monitored": true,
        "chainValue": 0,
        "chainValueZat": 0,
        "valueDelta": 0,
        "valueDeltaZat": 0
      }
    ],
    "previousblockhash": "01d1bfef50e079c53b36463fdf0ae55dc26b2205cd5f39c2bd030d19c2375e28",
    "nextblockhash": "0438bfda6a2706a622df7808fa5f4f32ac2e5d3039895ff8cb080d7e8e231188"
  },
  "error": null,
  "id": "curltest"
}
```

> You can find your rpcusername, rpcpassword, and rpcport in the coin's .conf file.

```
command:

curl --user myrpcuser:myrpcpassword --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "getblock", "params": ["120", false] }' -H 'content-type: text/plain;' http://127.0.0.1:myrpcport/

response:

{
  "result": "04000000285e37c2190d03bdc2395fcd05226bc25de50adf3f46363bc579e050efbfd1013163caf3ad654ee90412d51e6d77b559ae912397ae89df7c6d4fe1f7fbce81470000000000000000000000000000000000000000000000000000000000000000f2ce925b080f0f200b00ea624b040b9c73b7d68ecdf8caf81c513f9aa8679a3172b52b82c55400002403fc1abba5f415b1c422942835d46c7ba3e94665964da4c31e236c6cf9b3dfe6ffb65db10101000000010000000000000000000000000000000000000000000000000000000000000000ffffffff0401780101ffffffff011027000000000000232103c0259e1a166e53f6ccf094ce37c0843d4a013622603bc301b4eb0f89c7cce823acf1ce925b",
  "error": null,
  "id": "curltest"
}
```

**getblock hash|height ( verbose )**

The `getblock` method returns the block's relevant state information.

The verbose input is optional. The default value is true, and it will return a json object with information about the indicated block. If verbose is `false`, the command returns a string that is serialized hex-encoded data for the indicated block.

### Arguments:

Structure|Type|Description
---------|----|-----------
"hash|height"|(string, required)|the block hash or height
verbose|(boolean, optional, default=true)|true returns a json object, false returns hex-encoded data

### Response (verbose = true):

Structure|Type|Description
---------|----|-----------
{| |
  "hash"|(string)|the block hash (same as provided hash)
  "confirmations"|(numeric)|the number of confirmations, or -1 if the block is not on the main chain
  "size"|(numeric)|the block size
  "height"|(numeric)|the block height or index (same as provided height)
  "version"|(numeric)|the block version
  "merkleroot"|(string)|the merkle root
  "tx"| |
    [|(array of string)|the transaction ids
      "transaction_id" |(string)|the transaction id
      , ...| |
    ]| |
  "time"|(numeric)|the block time in seconds since epoch (Jan 1 1970 GMT)
  "nonce"|(numeric)|the nonce
  "bits"|(string)|the bits
  "difficulty"|(numeric)|the difficulty
  "previousblockhash"|(string)|the hash of the previous block
  "nextblockhash"|(string)|the hash of the next block
}

### Response:

Structure|Type|Description
---------|----|-----------
	"data"|(string)|a string that is serialized, hex-encoded data for the indicated block

## getblockchaininfo

```
command:

komodo-cli getblockchaininfo

response:

{
  "chain": "regtest",
  "blocks": 398,
  "headers": 398,
  "bestblockhash": "0dd66ee1f151c38f73843378c08715ee3f4d3cf2888783e2846b81c057987084",
  "difficulty": 1.000023305960651,
  "verificationprogress": 1,
  "chainwork": "0000000000000000000000000000000000000000000000000000000000001a7f",
  "pruned": false,
  "commitments": 0,
  "valuePools": [
    {
      "id": "sprout",
      "monitored": true,
      "chainValue": 0.00000000,
      "chainValueZat": 0
    }
  ],
  "softforks": [
    {
      "id": "bip34",
      "version": 2,
      "enforce": {
        "status": false,
        "found": 399,
        "required": 750,
        "window": 1000
      },
      "reject": {
        "status": false,
        "found": 399,
        "required": 950,
        "window": 1000
      }
    }
  ],
  "upgrades": {
  },
  "consensus": {
    "chaintip": "00000000",
    "nextblock": "00000000"
  }
}
```

> You can find your rpcusername, rpcpassword, and rpcport in the coin's .conf file.

```
command:

curl --user myrpcuser:myrpcpassword --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "getblockchaininfo", "params": [] }' -H 'content-type: text/plain;' http://127.0.0.1:myrpcport/

response:

{
  "result": {
    "chain": "regtest",
    "blocks": 398,
    "headers": 398,
    "bestblockhash": "0dd66ee1f151c38f73843378c08715ee3f4d3cf2888783e2846b81c057987084",
    "difficulty": 1.000023305960651,
    "verificationprogress": 1,
    "chainwork": "0000000000000000000000000000000000000000000000000000000000001a7f",
    "pruned": false,
    "commitments": 0,
    "valuePools": [
      {
        "id": "sprout",
        "monitored": true,
        "chainValue": 0,
        "chainValueZat": 0
      }
    ],
    "softforks": [
      {
        "id": "bip34",
        "version": 2,
        "enforce": {
          "status": false,
          "found": 399,
          "required": 750,
          "window": 1000
        },
        "reject": {
          "status": false,
          "found": 399,
          "required": 950,
          "window": 1000
        }
      }
    ],
    "upgrades": {},
    "consensus": {
      "chaintip": "00000000",
      "nextblock": "00000000"
    }
  },
  "error": null,
  "id": "curltest"
}
```

**getblockchaininfo**

The `getblockchaininfo` method returns a json object containing state information about blockchain processing.

<aside class="notice">
When the chain tip is at the last block before a network upgrade activation, the `consensus.chaintipc` value is not equal to the `consensus.nextblock` value.
</aside>

### Arguments:

Structure|Type|Description
---------|----|-----------
  (none)| |

### Response:

Structure|Type|Description
---------|----|-----------  
{| |
    "chain"|(string)|current network name as defined in BIP70 (main, test, regtest)
    "blocks"|(numeric)|the current number of blocks processed in the server
    "headers"|(numeric)|the current number of headers we have validated
    "bestblockhash"|(string)|the hash of the currently best block
    "difficulty"|(numeric)|the current difficulty
    "verificationprogress"|(numeric)|estimate of verification progress [0..1]
    "chainwork"|(string)|total amount of work in active chain, in hexadecimal
    "commitments"|(numeric)|the current number of note commitments in the commitment tree
    "softforks": [|(array)|status of softforks in progress
      {| |
        "id"|(string)|name of softfork
        "version"|(numeric)|block version
        "enforce": {|(object)|progress toward enforcing the softfork rules for new-version blocks
          "status"|(boolean)|true if threshold reached
          "found"|(numeric)|number of blocks with the new version found
          "required"|(numeric)|number of blocks required to trigger
          "window"|(numeric)|maximum size of examined window of recent blocks
        },| |
        "reject": {| | 
          ...|(object)|progress toward rejecting pre-softfork blocks (same fields as "enforce")
        }| |
      }, ...| |accepts multiple entries
    ],| |
    "upgrades": {|(object)|status of network upgrades
      "xxxxxxxxx_string": {|(string)|branch ID of the upgrade
          "name"|(string)|name of upgrade
          "activationheight"|(numeric)|block height of activation
          "status"|(string)|status of upgrade
          "info"|(string)|additional information about upgrade
      }, ...|accepts multiple entries
    },| |
    "consensus": {|(object)|branch IDs of the current and upcoming consensus rules
     "chaintip"|(string)|branch ID used to validate the current chain tip
     "nextblock"|(string)|branch ID that the next block will be validated under
    }| |
  }| |

## getblockcount

**getblockcount**

The `getblockcount` method returns the number of blocks in the best valid block chain.

### Arguments:

Structure|Type|Description
---------|----|-----------
(none)| |

### Response:

Structure|Type|Description
---------|----|-----------
data|(numeric)|the current block count

```
command:

komodo-cli getblockcount

response:

398
```

> You can find your rpcusername, rpcpassword, and rpcport in the coin's .conf file.

```
command:

curl --user myrpcuser:myrpcpassword --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "getblockcount", "params": [] }' -H 'content-type: text/plain;' http://127.0.0.1:myrpcport/

response:

{
  "result": 398,
  "error": null,
  "id": "curltest"
}
```

## getblockhash

```
  command:

  komodo-cli getblockhash 100

  response:

  08674c7a6ab6c40000d45e2094f2cafc6575bfcfdd1ce90fa0060fa573803024
```

> You can find your rpcusername, rpcpassword, and rpcport in the coin's .conf file.

```
  command:

	curl --user myrpcuser:myrpcpassword --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "getblockhash", "params": [1000] }' -H 'content-type: text/plain;' http://127.0.0.1:myrpcport/

  response:

  {
    "result": "08674c7a6ab6c40000d45e2094f2cafc6575bfcfdd1ce90fa0060fa573803024",
    "error": null,
    "id": "curltest"
  }
```

**getblockhash index**

The `getblockhash` method returns the hash of the indicated block index, according to the best blockchain at the time provided.

### Arguments:

Structure|Type|Description
---------|----|-----------
index|(numeric, required)|the block index

### Response:

Structure|Type|Description
---------|----|-----------
"hash"|(string)|the block hash

## getblockhashes

**getblockhashes high low '{"noOrphans": bool, "logicalTimes": bool}'**

The `getblockhashes` method returns an array of hashes of blocks within the timestamp range provided.

### Arguments:

Structure|Type|Description
---------|----|-----------
high|(numeric, required)|the newer block timestamp
low|(numeric, required)|the older block timestamp
options|(string, required)|
{| |
  "noOrphans"|(boolean)|will only include blocks on the main chain
  "logicalTimes"|(boolean)|will include logical timestamps with hashes
}| |

### Response:

Structure|Type|Description
---------|----|-----------
[| |
  "hash"|(string)|the block hash
]| |
[| |
  {| |
    "blockhash"|(string)|the block hash
    "logicalts"|(numeric)|the logical timestamp
  }| |
]| |

> You can find your rpcusername, rpcpassword, and rpcport in the coin's .conf file.

```
command:

komodo-cli getblockhashes 1231614698 1231024505

response:

```

```
command:

curl --user myrpcuser:myrpcpassword --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "getblockhashes", "params": [1231614698, 1231024505] }' -H 'content-type: text/plain;' http://127.0.0.1:myrpcport/

response:

```

```
command:

komodo-cli getblockhashes 1231614698 1231024505 '{"noOrphans":false, "logicalTimes":true}'

response:

```

## getblockheader

```
command:

komodo-cli getblockheader "00000000c937983704a73af28acdec37b049d214adbda81d7e2a3dd146f6ed09"

response:

{
  "hash": "0dd66ee1f151c38f73843378c08715ee3f4d3cf2888783e2846b81c057987084",
  "confirmations": 1,
  "height": 398,
  "version": 4,
  "merkleroot": "d6e8292d85181a177c21497a7e636fc4f1eef1fbd2887b3a19e1d72134429668",
  "time": 1536603968,
  "nonce": "00002474e66d5ef243d7b0a8eec32983492daf29e0b0887bd67b2107d1000004",
  "solution": "30a5e9153392b643d139cf205b270d55cb7d3b4779fd7a3666bdb744ef221c966fde1324",
  "bits": "200f0ef8",
  "difficulty": 1.000023305960651,
  "chainwork": "0000000000000000000000000000000000000000000000000000000000001a7f",
  "segid": -2,
  "previousblockhash": "09f9b547842b38a7748c8633eedb609b269138fdb3f2f75570fcb0d653fe42f4"
}
```

> You can find your rpcusername, rpcpassword, and rpcport in the coin's .conf file.

```
command:

curl --user myrpcuser:myrpcpassword --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "getblockheader", "params": ["0dd66ee1f151c38f73843378c08715ee3f4d3cf2888783e2846b81c057987084"] }' -H 'content-type: text/plain;' http://127.0.0.1:myrpcport/

response:

{
  "result": {
    "hash": "0dd66ee1f151c38f73843378c08715ee3f4d3cf2888783e2846b81c057987084",
    "confirmations": 1,
    "height": 398,
    "version": 4,
    "merkleroot": "d6e8292d85181a177c21497a7e636fc4f1eef1fbd2887b3a19e1d72134429668",
    "time": 1536603968,
    "nonce": "00002474e66d5ef243d7b0a8eec32983492daf29e0b0887bd67b2107d1000004",
    "solution": "30a5e9153392b643d139cf205b270d55cb7d3b4779fd7a3666bdb744ef221c966fde1324",
    "bits": "200f0ef8",
    "difficulty": 1.000023305960651,
    "chainwork": "0000000000000000000000000000000000000000000000000000000000001a7f",
    "segid": -2,
    "previousblockhash": "09f9b547842b38a7748c8633eedb609b269138fdb3f2f75570fcb0d653fe42f4"
  },
  "error": null,
  "id": "curltest"
}
```

**getblockheader "hash" ( verbose )**

The `getblockheader` method returns information about the indicated block.

The verbose input is optional. If verbose is false, the method returns a string that is serialized, hex-encoded data for the indicated blockheader. If verbose is true, the method returns a json object with information about the indicated blockheader.

### Arguments:

Structure|Type|Description
---------|----|-----------
"hash"|(string, required)|the block hash
	verbose|(boolean, optional, default=true)|true returns a json object, false returns hex-encoded data

### Response (verbose = `true`):

Structure|Type|Description
---------|----|-----------
{| |
  "hash"|(string)|the block hash (same as provided)
  "confirmations"|(numeric)|the number of confirmations, or -1 if the block is not on the main chain
  "height"|(numeric)|the block height or index
  "version"|(numeric)|the block version
  "merkleroot"|(string)|the merkle root
  "time"|(numeric)|the block time in seconds since epoch (Jan 1 1970 GMT)
  "nonce"|(numeric)|the nonce
  "bits"|(string)|the bits
  "difficulty"|(numeric)|the difficulty
  "previousblockhash"|(string)|the hash of the previous block
  "nextblockhash"|(string)|the hash of the next block
}| |

### Response (verbose = `false`):

Structure|Type|Description
---------|----|-----------
"data"|(string)|a string that is serialized hex-encoded data for the indicated block

getchaintips
------------

  getchaintips

The `getchaintips` method returns information about all known tips in the block tree, including the main chain and any orphaned branches.

### Arguments:

Structure|Type|Description
---------|----|-----------
  (none)

### Response:

Structure|Type|Description
---------|----|-----------	[
	  {
	    "height"              (numeric)    height of the chain tip
	    "hash"                (string)     block hash of the tip
	    "branchlen"           (numeric)    zero for main chain
	    "status"              (string)     "active" for the main chain
	  },
	  {
	    "height"              (numeric)    height of the branch tip
	    "hash"                (string)     blockhash of the branch tip
	    "branchlen"           (numeric)    length of branch connecting the tip to the main chain
	    "status"              (string)     status of the chain
	  }
	]

Possible values for status:

	 "invalid"               this branch contains at least one invalid block
	 "headers-only"          not all blocks for this branch are available, but the headers are valid
	 "valid-headers"         all blocks are available for this branch, but they were never fully validated
	"valid-fork"            this branch is not part of the active chain, but is fully validated
	"active"                this is the tip of the active main chain, which is certainly valid

> You can find your rpcusername, rpcpassword, and rpcport in the coin's .conf file.

```
  command:

	komodo-cli getchaintips

  response:

  [
    {
      "height": 398,
      "hash": "0dd66ee1f151c38f73843378c08715ee3f4d3cf2888783e2846b81c057987084",
      "branchlen": 0,
      "status": "active"
    }
  ]
```

```
  command:

  curl --user myrpcuser:myrpcpassword --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "getchaintips", "params": [] }' -H 'content-type: text/plain;' http://127.0.0.1:myrpcport/

  response:

  {
    "result": [
      {
        "height": 398,
        "hash": "0dd66ee1f151c38f73843378c08715ee3f4d3cf2888783e2846b81c057987084",
        "branchlen": 0,
        "status": "active"
      }
    ],
    "error": null,
    "id": "curltest"
  }

getdifficulty
-------------

  getdifficulty

The `getdifficulty` method returns the proof-of-work difficulty as a multiple of the minimum difficulty.

### Arguments:

Structure|Type|Description
---------|----|-----------
  (none)

### Response:

Structure|Type|Description
---------|----|-----------	number            (numeric)  the proof-of-work difficulty as a multiple of the minimum difficulty

> You can find your rpcusername, rpcpassword, and rpcport in the coin's .conf file.

```
  command:

	komodo-cli getdifficulty

  response:

  1.000023305960651

```

```
  command:

  curl --user myrpcuser:myrpcpassword --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "getdifficulty", "params": [] }' -H 'content-type: text/plain;' http://127.0.0.1:myrpcport/

  response:

  {
    "result": 1.000023305960651,
    "error": null,
    "id": "curltest"
  }

getmempoolinfo
--------------

  getmempoolinfo

The `getmempoolinfo` method returns details on the active state of the transaction memory pool.

### Arguments:

Structure|Type|Description
---------|----|-----------
  (none)

### Response:

Structure|Type|Description
---------|----|-----------	{
	  "size"                (numeric)    current tx count
	  "bytes"               (numeric)    sum of all tx sizes
	  "usage"               (numeric)    total memory usage for the mempool
	}

> You can find your rpcusername, rpcpassword, and rpcport in the coin's .conf file.

```
  command:

	komodo-cli getmempoolinfo

  response:

  {
    "size": 1,
    "bytes": 226,
    "usage": 896
  }
```

```
  command:

  curl --user myrpcuser:myrpcpassword --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "getmempoolinfo", "params": [] }' -H 'content-type: text/plain;' http://127.0.0.1:myrpcport/

  response:

  {
    "result": {
      "size": 1,
      "bytes": 226,
      "usage": 896
    },
    "error": null,
    "id": "curltest"
  }

getrawmempool
-------------

  getrawmempool ( verbose )

The `getrawmempool` method returns all transaction ids in the memory pool as a json array of transaction ids.

The verbose input is optional and is false by default. When it is true, the method instead returns a json object with various related data.

### Arguments:

Structure|Type|Description
---------|----|-----------
	verbose               (boolean, optional, default=false)     true for a json object, false for a json array of transaction ids

Response (verbose = `false` ):

	[
	  "transaction_id"                (string)    the transaction id
	  , ...
	]

Response (verbose = `true` ):

	{
	  "transaction_id" : {
	    "size"                       (numeric)   transaction size in bytes
	    "fee"                        (numeric)   transaction fee
    	"time"                       (numeric)   local time transaction entered pool in seconds since 1 Jan 1970 GMT
    	"height"                     (numeric)   block height when transaction entered pool
    	"startingpriority"           (numeric)   priority when transaction entered pool
    	"currentpriority"            (numeric)   transaction priority now
    	"depends": [                 (array)     unconfirmed transactions used as inputs for this transaction
        "transaction_id"            (string)    parent transaction id
	       , ...
      ]
	  }, ...
	}

> You can find your rpcusername, rpcpassword, and rpcport in the coin's .conf file.

```
  command:

  komodo-cli getrawmempool true

  response:

  {
    "44760f145303cae081819c6e54665d6716c98e97691603b4edf133b8180e6048": {
      "size": 488,
      "fee": 0.00011462,
      "time": 1536618366,
      "height": 448,
      "startingpriority": 20910198.65384615,
      "currentpriority": 20910198.65384615,
      "depends": [
      ]
    }
  }
```

```
  command:

	curl --user myrpcuser:myrpcpassword --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "getrawmempool", "params": [true] }' -H 'content-type: text/plain;' http://127.0.0.1:myrpcport/

  response:

  {
    "result": {
      "44760f145303cae081819c6e54665d6716c98e97691603b4edf133b8180e6048": {
        "size": 488,
        "fee": 0.00011462,
        "time": 1536618366,
        "height": 448,
        "startingpriority": 20910198.65384615,
        "currentpriority": 20910198.65384615,
        "depends": []
      }
    },
    "error": null,
    "id": "curltest"
  }

getspentinfo
------------

  getspentinfo '{"txid": "txid_string", "index", block_height_number}'

The `getspentinfo` method returns the transaction id and index where an output is spent.

### Arguments:

Structure|Type|Description
---------|----|-----------
	{
	  "txid"            (string)     the hex string of the txid
	  "index"           (number)     the start block height
	}

### Response:

Structure|Type|Description
---------|----|-----------	{
	  "txid"            (string)     the transaction id
	  "index"           (number)     the spending input index
	  , ...
	}

> You can find your rpcusername, rpcpassword, and rpcport in the coin's .conf file.

```
  command:

	komodo-cli getspentinfo '{"txid": "41ec75822318373bd00513efe7c708e745ab370db08ef4e0bd2ba4882ea77b40", "index": 0}'

  response:

  curl --user myrpcuser:myrpcpassword --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "getspentinfo", "params": [{"txid": "41ec75822318373bd00513efe7c708e745ab370db08ef4e0bd2ba4882ea77b40", "index": 0}] }' -H 'content-type: text/plain;' http://127.0.0.1:myrpcport/

gettxout
--------

  gettxout "txid_string" vout_number ( includemempool_bool )

The `gettxout` method returns details about an unspent transaction output.

### Arguments:

Structure|Type|Description
---------|----|-----------
	"txid"                      (string, required)     the transaction id
	vout                        (numeric, required)    vout value
	includemempool              (boolean, optional)    whether to include the mempool

### Response:

Structure|Type|Description
---------|----|-----------	{
	  "bestblock"               (string)               the block hash
	  "confirmations"           (numeric)              the number of confirmations
	  "value"                   (numeric)              the transaction value
  	"scriptPubKey": {
    	 "asm"                  (string)
    	 "hex"                  (string)
    	 "reqSigs"              (numeric)              number of required signatures
    	 "type"                 (string)               the type, e.g. pubkeyhash
    	 "addresses" : [        (array of strings)     array of addresses
    	    "address"      (string)               address on blockchain
    	    , ...
    	 ]
  	},
  	"version"                 (numeric)              the version
  	"coinbase"                (boolean)              coinbase or not
	}

Examples:

  command:

	komodo-cli gettxout "txid" 1

  response:

  {
    "bestblock": "0e398d8d00f7846f28b47a6c0da16b14002441f5a5340b6d492060c698bdd84c",
    "confirmations": 252,
    "value": 0.00010000,
    "scriptPubKey": {
      "asm": "03c0259e1a166e53f6ccf094ce37c0843d4a013622603bc301b4eb0f89c7cce823 OP_CHECKSIG",
      "hex": "2103c0259e1a166e53f6ccf094ce37c0843d4a013622603bc301b4eb0f89c7cce823ac",
      "reqSigs": 1,
      "type": "pubkey",
      "addresses": [
        "RM1mKzZDEr462UBqVjXSKXR3F83yMpG3Ue"
      ]
    },
    "version": 1,
    "coinbase": true
  }
```

```
  command:

	curl --user myrpcuser:myrpcpassword --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "gettxout", "params": ["txid", 1] }' -H 'content-type: text/plain;' http://127.0.0.1:myrpcport/

  response:

  {
    "result": {
      "bestblock": "0e398d8d00f7846f28b47a6c0da16b14002441f5a5340b6d492060c698bdd84c",
      "confirmations": 252,
      "value": 0.0001,
      "scriptPubKey": {
        "asm": "03c0259e1a166e53f6ccf094ce37c0843d4a013622603bc301b4eb0f89c7cce823 OP_CHECKSIG",
        "hex": "2103c0259e1a166e53f6ccf094ce37c0843d4a013622603bc301b4eb0f89c7cce823ac",
        "reqSigs": 1,
        "type": "pubkey",
        "addresses": [
          "RM1mKzZDEr462UBqVjXSKXR3F83yMpG3Ue"
        ]
      },
      "version": 1,
      "coinbase": true
    },
    "error": null,
    "id": "curltest"
  }

gettxoutproof
-------------

  gettxoutproof '["transaction_id", ... ]' ( "blockhash_string" )

The `gettxoutproof` method returns a hex-encoded proof showing that the indicated transaction was included in a block.

**NOTE:** The `gettxoutproof` method relies on the ===link=== `txindex` runtime parameter. This parameter is enabled by default on all KMD-based blockchains, and should never be disabled.

### Arguments:

Structure|Type|Description
---------|----|-----------
  [
    "txid"                 (string)               a transaction hash
    , ...                     accepts multiple entries
  ]
	"blockhash"              (string, optional)     if specified, looks for the relevant txid in this block

### Response:

Structure|Type|Description
---------|----|-----------	"data"                          (string)               a string that is a serialized, hex-encoded data for the proof

> You can find your rpcusername, rpcpassword, and rpcport in the coin's .conf file.

```
  command:

  komodo-cli gettxoutproof '["c71f4a2ebf87bdd588e3aa168917933ee4be1661245ebf52d5708a8339cf9d7a"]' "0a28e2fb630b282138bf23bb79f597b11acff6f57c8d9c1c10fa54770035c813"

  response:

  040000004cd8bd98c66020496d0b34a5f5412400146ba10d6c7ab4286f84f7008d8d390e9ca9575183f60906e293e9766997396bec59f1c0b966085de3d17f8ac3c9d5280000000000000000000000000000000000000000000000000000000000000000da05975bf50e0f202d004b81fcc388cfd411d8c7c59a548e070b5affe938ce8ce830f10b298b00002402939a9a31df1305b40d26d9748283b102c708258717248d0d63f01d2957d8e3dcf56f6e03000000022e4babc29707fbdd8da2e4277b7c8b8b09e837f409eb047c936904d75fc8e6267a9dcf39838a70d552bf5e246116bee43e93178916aae388d5bd87bf2e4a1fc7010d

gettxoutsetinfo
---------------

  gettxoutsetinfo

The `gettxoutsetinfo` method returns statistics about the unspent transaction output set.

* Note this call may take a long time to complete, depending on the state of your blockchain.

Arguments

  (none)

### Response:

Structure|Type|Description
---------|----|-----------	{
	  "height"                (numeric)        the current block height (index)
	  "bestblock"             (string)         the best block hash hex
	  "transactions"          (numeric)        the number of transactions
	  "txouts"                (numeric)        the number of output transactions
 	  "bytes_serialized"      (numeric)        the serialized size
	  "hash_serialized"       (string)         the serialized hash
	  "total_amount"          (numeric)        the total amount
	}

> You can find your rpcusername, rpcpassword, and rpcport in the coin's .conf file.

```
	command:

  komodo-cli gettxoutsetinfo

  response:

  {
    "height": 459,
    "bestblock": "0a28e2fb630b282138bf23bb79f597b11acff6f57c8d9c1c10fa54770035c813",
    "transactions": 258,
    "txouts": 261,
    "bytes_serialized": 18051,
    "hash_serialized": "fdd2039fa21400be0928b26dfe534f543dc5090989bcbd97fdc81b30ce7dca3a",
    "total_amount": 10.16456229
  }
```

```
  command:

  curl --user myrpcuser:myrpcpassword --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "gettxoutsetinfo", "params": [] }' -H 'content-type: text/plain;' http://127.0.0.1:myrpcport/

  response:

  {
    "result": {
      "height": 459,
      "bestblock": "0a28e2fb630b282138bf23bb79f597b11acff6f57c8d9c1c10fa54770035c813",
      "transactions": 258,
      "txouts": 261,
      "bytes_serialized": 18051,
      "hash_serialized": "fdd2039fa21400be0928b26dfe534f543dc5090989bcbd97fdc81b30ce7dca3a",
      "total_amount": 10.16456229
    },
    "error": null,
    "id": "curltest"
  }

kvsearch
--------

  kvsearch "key_string"

The `kvsearch` method searches for a key stored via the ===link=== `kvupdate` command.

 * Note: This feature is only available for asset chains.

### Arguments:

Structure|Type|Description
---------|----|-----------
  key               (string, required)    search the chain for this key

### Response:

Structure|Type|Description
---------|----|-----------  {
    "coin"            (string)              chain the key is stored on
    "currentheight"   (numeric)             current height of the chain
    "key"             (string)              key
    "keylen"          (string)              length of the key
    "owner"           (string)              hex string representing the owner of the key
    "height"          (numeric)             height the key was stored at
    "expiration"      (numeric)             height the key will expire
    "flags": x        (numeric)             1 if the key was created with a password; 0 otherwise
    "value"           (string)              stored value
    "valuesize"       (string)              amount of characters stored
  }

Examples:

  command:

  komodo-cli kvsearch examplekey

  response:

  {
    "coin": "MYCOIN",
    "currentheight": 566,
    "key": "examplekey",
    "keylen": 10,
    "owner": "1ff91604c6adb6ec550e7575fe9f1ca591704572e125f55bed03a21c242c31b7",
    "height": 561,
    "expiration": 2001,
    "flags": 0,
    "value": "examplevalue",
    "valuesize": 12
  }
```

```
  command:

  curl --user myrpcuser:myrpcpassword --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "kvsearch", "params": ["examplekey"] }' -H 'content-type: text/plain;' http://127.0.0.1:myrpcport/

  response:

  {
    "result": {
      "coin": "MYCOIN",
      "currentheight": 566,
      "key": "examplekey",
      "keylen": 10,
      "owner": "1ff91604c6adb6ec550e7575fe9f1ca591704572e125f55bed03a21c242c31b7",
      "height": 561,
      "expiration": 2001,
      "flags": 0,
      "value": "examplevalue",
      "valuesize": 12
    },
    "error": null,
    "id": "curltest"
  }


kvupdate
--------

  kvupdate "key_string" "value_string" days "passphrase_string"

The `kvupdate` method stores a key/value pair via OP_RETURN.

This feature is available only for asset chains. The maximum value memory size is 8kB.

### Arguments:

Structure|Type|Description
---------|----|-----------
  "key"                    (string, required)     key (should be unique)
  "value"                  (string, required)     value
  "days"                   (numeric, required)    amount of days before the key expires (1440 blocks/day); minimum 1 day
  "passphrase"             (string, optional)     passphrase required to update this key

### Response:

Structure|Type|Description
---------|----|-----------  {
    "coin"                 (string)               chain the key is stored on
    "height"               (numeric)              height the key was stored at
    "expiration"           (numeric)              height the key will expire
    "flags"                (string)               amount of days the key will be stored
    "key"                  (numeric)              stored key
    "keylen"               (numeric)              length of the key
    "value"                (numeric)              stored value
    "valuesize"            (string)               length of the stored value
    "fee"                  (string)               transaction fee paid to store the key
    "txid"                 (string)               transaction id
  }

Examples:

  command:

  komodo-cli kvupdate "examplekey" "examplevalue" 2 "examplepassphrase"

  response:

  {
    "coin": "MYCOIN",
    "owner": "1ff91604c6adb6ec550e7575fe9f1ca591704572e125f55bed03a21c242c31b7",
    "height": 566,
    "expiration": 2006,
    "flags": 3,
    "key": "examplekey",
    "keylen": 10,
    "value": "examplevalue",
    "valuesize": 12,
    "fee": 0.001,
    "txid": "2dc76f39188bb006931a2c924fdf66bc3baf149bf880fffad778cabd6ace5749"
  }
```

```
  command:

  curl --user myrpcuser:myrpcpassword --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "kvupdate", "params": ["examplekey", "examplevalue", "2", "examplepassphrase"] }' -H 'content-type: text/plain;' http://127.0.0.1:9801

  response:

  {
    "result": {
      "coin": "MYCOIN",
      "owner": "1ff91604c6adb6ec550e7575fe9f1ca591704572e125f55bed03a21c242c31b7",
      "height": 566,
      "expiration": 2006,
      "flags": 3,
      "key": "examplekey",
      "keylen": 10,
      "value": "examplevalue",
      "valuesize": 12,
      "fee": 0.001,
      "txid": "9f44dc664882198b14e9a8c466d466efcdd070ccb6f57be8e2884aa11e7b2a30"
    },
    "error": null,
    "id": "curltest"
  }

minerids
--------

  minerids height

The `minerids` method returns information about the notary nodes and external miners at a specific block height. The response will calculate results according to the 2000 blocks proceeding the indicated "height" block.

### Arguments:

Structure|Type|Description
---------|----|-----------
  heights                  (number)   the block height for the query

### Response:

Structure|Type|Description
---------|----|-----------  {
    "mined": [
      {
        "notaryid"         (number)   the id of the specific notary node
        "kmdaddress"       (string)   the KMD address of the notary node
        "pubkey"           (string)   the public signing key of the notary node
        "blocks"           (number)
      }
    ]
  }

Examples:


  command:

  komodo-cli minerids 1000000

  response:

  {
    "mined": [
      {
        "notaryid": 0,
        "KMDaddress": "RNJmgYaFF5DbnrNUX6pMYz9rcnDKC2tuAc",
        "pubkey": "03b7621b44118017a16043f19b30cc8a4cfe068ac4e42417bae16ba460c80f3828",
        "blocks": 22
      }
        ...    (63 responses omitted for brevity)
      ,
      {
        "pubkey": "external miners",
        "blocks": 541
      }
    ],
    "numnotaries": 64
  }
```

```
  command:

  curl --user myrpcuser:myrpcpassword --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "minerids", "params": ["1000000"] }' -H 'content-type: text/plain;' http://127.0.0.1:myrpcport/

  response:

  {
    "result": {
      "mined": [
        {
          "notaryid": 0,
          "KMDaddress": "RNJmgYaFF5DbnrNUX6pMYz9rcnDKC2tuAc",
          "pubkey": "03b7621b44118017a16043f19b30cc8a4cfe068ac4e42417bae16ba460c80f3828",
          "blocks": 22
        }
          ...    (63 responses omitted for brevity)
        ,
        {
          "pubkey": "external miners",
          "blocks": 541
        }
      ],
      "numnotaries": 64
    },
    "error": null,
    "id": "curltest"
  }

notaries height timestamp
---------

  notaries height timestamp

  notaries height

  notaries timestamp

The `notaries` method returns the public key, BTC address, and KMD address for each Komodo notary node.

Either or both of the height and timestamp parameters will suffice.

### Arguments:

Structure|Type|Description
---------|----|-----------
                                      (at least one of the inputs must be provided)
  height                 (number)     the block height desired for the query
  timestamp              (number)     the timestamp of the block desired for the query

### Response:

Structure|Type|Description
---------|----|-----------  {
    "notaries": [
      {
        "pubkey"         (string)       the public signing key of the indicated notary node, used on the KMD network to create notary-node authorized transactions
        "BTCaddress"     (string)       the public BTC address the notary node uses on the BTC blockchain to create notarizations
        "KMDaddress"     (string)       the public KMD address the notary node uses on the KMD blockchain to create notarizations
      }
      ,  ...                            property will return typically 64 objects
    ],
    "numnotaries"        (number)       the number of notary nodes; typically it is 64, but may vary on rare circumstances, such as during election seasons
    "height"             (number)       the block height number at which the notary-node information applies
    "timestamp"          (number)       the timestamp at which the notary-node information applies
  }

Examples:

 * Note: Information about myrpcuser, myrpcpassword, and myrpcport can be found in the coin's .conf file.

  command:

  komodo-cli notaries 1536365515

  response:

  {
    "notaries": [
      {
        "pubkey": "03b7621b44118017a16043f19b30cc8a4cfe068ac4e42417bae16ba460c80f3828",
        "BTCaddress": "1E2ac2gxeFR2ir1H3vqETTperWkiXkwy99",
        "KMDaddress": "RNJmgYaFF5DbnrNUX6pMYz9rcnDKC2tuAc"
      },
        ...  (63 responses omitted from the documentation for brevity)
    ],
    "numnotaries": 64,
    "height": 1536365515,
    "timestamp": 1536792974
  }
```

```
  command:
  curl --user myrpcuser:myrpcpassword --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "notaries", "params": ["1000000"] }' -H 'content-type: text/plain;' http://127.0.0.1:myrpcport/

  response:

  {
  "result": {
    "notaries": [
      {
        "pubkey": "03b7621b44118017a16043f19b30cc8a4cfe068ac4e42417bae16ba460c80f3828",
        "BTCaddress": "1E2ac2gxeFR2ir1H3vqETTperWkiXkwy99",
        "KMDaddress": "RNJmgYaFF5DbnrNUX6pMYz9rcnDKC2tuAc"
      },
        ...      (63 responses omitted from documentation for brevity)
    ],
    "numnotaries": 64,
    "height": 1000000,
    "timestamp": 1536365515
  },
  "error": null,
  "id": "curltest"
}

verifychain
-----------

  verifychain ( checklevel numblocks )

The `verifychain` method verifies the coin daemon's blockchain database.

 * Note: depending on the state of your blockchain database and daemon, this call can take a prolonged period of time to complete.

### Arguments:

Structure|Type|Description
---------|----|-----------
	checklevel          (numeric, optional, 0-4, default=3)        indicates the thoroughness of block verification
	numblocks           (numeric, optional, default=288, 0=all)    indicates the number of blocks to verify

### Response:

Structure|Type|Description
---------|----|-----------	true|false          (boolean)                                  verification was successful or unsuccessful

> You can find your rpcusername, rpcpassword, and rpcport in the coin's .conf file.

```
  command:

	komodo-cli verifychain

  response:

  true
```

```
  command:

  curl --user myrpcuser:myrpcpassword --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "verifychain", "params": [] }' -H 'content-type: text/plain;' http://127.0.0.1:myrpcport/

  response:

  {
    "result": true,
    "error": null,
    "id": "curltest"
  }

verifytxoutproof


  verifytxoutproof "proof_string"

The `verifytxoutproof` method verifies that a proof points to a transaction in a block. It returns the transaction to which the proof is committed, or it will throw an RPC error if the block is not in the current best chain.

### Arguments:

Structure|Type|Description
---------|----|-----------
	"proof_string"            (string, required)       the hex-encoded proof generated by gettxoutproof

### Response:

Structure|Type|Description
---------|----|-----------	[
    "txid"                  (string)         the transaction ids which the proof commits to; the array is empty if the proof is invalid
  ]

Examples:

  command:

  komodo-cli verifytxoutproof "040000004cd8bd98c66020496d0b34a5f5412400146ba10d6c7ab4286f84f7008d8d390e9ca9575183f60906e293e9766997396bec59f1c0b966085de3d17f8ac3c9d5280000000000000000000000000000000000000000000000000000000000000000da05975bf50e0f202d004b81fcc388cfd411d8c7c59a548e070b5affe938ce8ce830f10b298b00002402939a9a31df1305b40d26d9748283b102c708258717248d0d63f01d2957d8e3dcf56f6e03000000022e4babc29707fbdd8da2e4277b7c8b8b09e837f409eb047c936904d75fc8e6267a9dcf39838a70d552bf5e246116bee43e93178916aae388d5bd87bf2e4a1fc7010d"

  response:

  [
    "c71f4a2ebf87bdd588e3aa168917933ee4be1661245ebf52d5708a8339cf9d7a"
  ]
```

```
  command:

  curl --user myrpcuser:myrpcpassword --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "verifytxoutproof", "params": ["040000004cd8bd98c66020496d0b34a5f5412400146ba10d6c7ab4286f84f7008d8d390e9ca9575183f60906e293e9766997396bec59f1c0b966085de3d17f8ac3c9d5280000000000000000000000000000000000000000000000000000000000000000da05975bf50e0f202d004b81fcc388cfd411d8c7c59a548e070b5affe938ce8ce830f10b298b00002402939a9a31df1305b40d26d9748283b102c708258717248d0d63f01d2957d8e3dcf56f6e03000000022e4babc29707fbdd8da2e4277b7c8b8b09e837f409eb047c936904d75fc8e6267a9dcf39838a70d552bf5e246116bee43e93178916aae388d5bd87bf2e4a1fc7010d"] }' -H 'content-type: text/plain;' http://127.0.0.1:9801

  response:

  {
    "result": [
      "c71f4a2ebf87bdd588e3aa168917933ee4be1661245ebf52d5708a8339cf9d7a"
    ],
    "error": null,
    "id": "curltest"
  }
