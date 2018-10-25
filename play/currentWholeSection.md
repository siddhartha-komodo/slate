## setgenerate

> Turn on generation with unlimited processors:

```
command:

komodo-cli setgenerate true -1

response:

(none)
```

> Check the setting:

```
command:

komodo-cli getgenerate

response:

true
```

> Turn off generation:

```
command:

komodo-cli setgenerate false

response:

(none)
```

> Turning the setting on via json rpc:

```
command:

curl --user myrpcuser:myrpcpassword --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "setgenerate", "params": [true, 1] }' -H 'content-type: text/plain;' http://127.0.0.1:myrpcport/

response:

{
  "result": null,
  "error": null,
  "id": "curltest"
}
```

**setgenerate generate ( genproclimit )**

The `setgenerate` method allows the user to set the `generate` property in the coin daemon to `true` or `false`, thus turning generation (mining) on or off.

Generation is limited to [`genproclimit`](## genproclimit) processors. Set `genproclimit` to `-1` for unlimited.

<aside class="notice">
  See also the [`getgenerate`](## getgenerate) method to query the current setting, and [`genproclimit`](##genproclimit) for setting processor default parameters.
</aside>

### Arguments:

Structure|Type|Description
---------|----|-----------
generate                                     |(boolean, required)          |set to true to turn on generation; set to off to turn off generation
genproclimit                                 |(numeric, optional)          |set the processor limit for when generation is on; use value "-1" for unlimited


### Response:

Structure|Type|Description
---------|----|-----------
(none)
