Adding more RPC calls to the blockchain source 
------------------------------------------------

This phase requires students to add custom RPC calls to the dash source code : 

* Add RPC call to the code that counts Orphan Blocks 

The RPC call should respond to:

```
./dash-cli -regtest getorphanblockcount
```

Please not that the logic for this RPC call should be written, its not currently there in the source.

* Add RPC call to check the Misbehaving score for a node where node\_id is the ID for the respective node we need the score for.

The RPC call should respond to:

```
./dash-cli -regtest getmisbehavingscore node_id
```











