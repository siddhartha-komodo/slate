z_validatepaymentdisclosure
---------------------------

::

  z_validatepaymentdisclosure "paymentdisclosure"

The ``z_validatepaymentdisclosure`` method validates a payment disclosure.

**EXPERIMENTAL FEATURE**

**WARNING**: Payment disclosure is currently DISABLED. This call always fails.

Arguments:

::

	"paymentdisclosure"       (string, required)   hex data string, with "zpd:" prefix

Examples:

::

  command:

  komodo-cli z_validatepaymentdisclosure "zpd:706462ff004c561a0447ba2ec51184e6c204..."

  response:

  (currently disabled)

::

  command:

  curl --user myrpcuser:myrpcpassword --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "z_validatepaymentdisclosure", "params": ["zpd:706462ff004c561a0447ba2ec51184e6c204..."] }' -H 'content-type: text/plain;' http://127.0.0.1:myrpcport/

  response:

  (currently disabled)
