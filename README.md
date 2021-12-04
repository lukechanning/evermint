# Evermint Blockchain

An extremely simple blockchain developed in Rust, based on the tutorial [provided here](https://blog.logrocket.com/how-to-build-a-blockchain-in-rust/#writing-a-blockchain-app-in-rust).

To fire it up, run:

```bash
RUST_LOG=info cargo run
```

This creates a local client for the blockchain. To simulate a distributed network, it's recommended that you run this command in multiple terminals. You should be able to see the nodes connect to each other and nodes should appear in the `ls p` output.

In each client, you can enter the following commands:

- `ls p` - list peers
- `ls c` - print local chain
- `create b $data` - `$data` is just a string here - this creates (mines) a new block with the data entry `$data` and broadcasts it

### Block Creation
When a block has been created, it's broadcasted to all other nodes on the network. If it is valid, it's accepted by the local blockchain at each node.

On startup, each node will request the blockchain from another node on the network. If the provided chain is longer and valid, the local blockchain is initialized with the provided one. This behavior will default to keeping the longest chain it receives. 

### To-Dos:
- Networking seems buggy and often creates broken pipes, debugging would be good
- If a chain becomes out of sync, the node is a throwaway
- Good documentation for all methods would be nice

