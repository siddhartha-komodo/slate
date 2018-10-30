{                                            |                             |
"chain"                                      |(string)                     |current network name as defined in BIP70 (main, test, regtest)
"blocks"                                     |(numeric)                    |the current number of blocks processed in the server
"headers"                                    |(numeric)                    |the current number of headers we have validated
"bestblockhash"                              |(string)                     |the hash of the currently best block
"difficulty"                                 |(numeric)                    |the current difficulty
"verificationprogress"                       |(numeric)                    |estimate of verification progress [0..1]
"chainwork"                                  |(string)                     |total amount of work in active chain, in hexadecimal
"size_on_disk"                               |(numeric)                    |the size of the blockchain on disk, measured in bytes
"commitments"                                |(numeric)                    |the current number of note commitments in the commitment tree
"softforks":                                 |                             |
{                                            |                             |
"id"                                         |(string)                     |name of softfork
"version"                                    |(numeric)                    |block version
"enforce":                                   |                             |
"status"                                     |(boolean)                    |true if threshold reached
"found"                                      |(numeric)                    |number of blocks with the new version found
"required"                                   |(numeric)                    |number of blocks required to trigger
"window"                                     |(numeric)                    |maximum size of examined window of recent blocks
},                                           |                             |
"reject":                                    |                             |
...                                          |(object)                     |progress toward rejecting pre-softfork blocks (same fields as "enforce")
}                                            |                             |
},                                           |                             |
],                                           |                             |
"upgrades":                                  |                             |
"xxxxxxxxx_string":                          |                             |
"name"                                       |(string)                     |name of upgrade
"activationheight"                           |(numeric)                    |block height of activation
"status"                                     |(string)                     |status of upgrade
"info"                                       |(string)                     |additional information about upgrade
},                                           |                             |
},                                           |                             |
"consensus":                                 |                             |
"chaintip"                                   |(string)                     |branch ID used to validate the current chain tip
"nextblock"                                  |(string)                     |branch ID that the next block will be validated under
}                                            |                             |
}                                            |                             |
