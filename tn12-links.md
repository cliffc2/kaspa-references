rusty-kaspa testnet (tn12)
https://github.com/kaspanet/rusty-kaspa/tree/covpp-reset2

kaswallet
https://github.com/IgraLabs/kaswallet

igra rpc provider
https://github.com/IgraLabs/igra-rpc-provider

cli
https://github.com/kaspanet/rusty-kaspa/tree/tn12/cli

kaspa crypto 
https://github.com/kaspanet/rusty-kaspa/tree/tn12/crypto

template
https://github.com/kaspanet/rusty-kaspa/blob/tn12/cli/src/modules/_template.rs

address
https://github.com/kaspanet/rusty-kaspa/blob/tn12/cli/src/modules/address.rs

keys
https://github.com/kaspanet/rusty-kaspa/tree/tn12/wallet/keys/src

private key generation
https://github.com/kaspanet/rusty-kaspa/blob/tn12/wallet/keys/src/privkeygen.rs

derivation
https://github.com/kaspanet/rusty-kaspa/tree/tn12/wallet/keys/src/derivation

details
https://github.com/kaspanet/rusty-kaspa/blob/tn12/cli/src/modules/details.rs

transaction
https://github.com/kaspanet/rusty-kaspa/blob/tn12/cli/src/extensions/transaction.rs

reate-unsigned-tx
https://github.com/kaspanet/rusty-kaspa/blob/tn12/cli/src/modules/create-unsigned-tx.rs

broadcast
https://github.com/kaspanet/rusty-kaspa/blob/tn12/cli/src/modules/broadcast.rs

cli modules
https://github.com/kaspanet/rusty-kaspa/tree/tn12/cli/src/modules

cli wizard
https://github.com/kaspanet/rusty-kaspa/blob/tn12/cli/src/cli.rs

rpc
https://github.com/kaspanet/rusty-kaspa/tree/tn12/rpc

rpc tests
https://github.com/kaspanet/rusty-kaspa/blob/tn12/testing/integration/src/rpc_tests.rs

protocols
https://github.com/kaspanet/rusty-kaspa/tree/tn12/protocol/p2p

integrating with kaspa
https://kaspa-mdbook.aspectron.com/rpc.html

reference for atomic swaps with eth  
https://docs.metamask.io/services/tutorials/ethereum/send-a-transaction/use-rust/

Transactions, Blocks, BlockDAG, Finality and Pruning, Pruning, Timelocks, API, P2P, RPC, Wallet
https://github.com/kaspanet/docs/tree/main/Reference

data_stack
https://github.com/kaspanet/rusty-kaspa/blob/tn12/crypto/txscript/src/data_stack.rs#L215

workflow rpc
https://github.com/workflow-rs/workflow-rs/tree/master/rpc

working silverscript webpage
https://silverscriptstudio.com/

covenant
// Build the expected output script
byte[34] recipientSpk = new ScriptPubKeyP2PK(recipient);

// Enforce: first output MUST go to recipient
require(tx.outputs[0].scriptPubKey == recipientSpk);

// Optionally enforce minimum value
require(tx.outputs[0].value >= 10000 litras);
Key concepts
ScriptPubKeyP2PK
Constructs a P2PK locking script from a public key. This is what an "address" looks like at the script level.
tx.outputs[i]
Access the i-th output of the spending transaction. You can read its .scriptPubKey and .value.
Covenant vs Lock
A lock checks who can spend. A covenant checks how they spend. Covenants are strictly more powerful.



wasm (gRPC is not supported by WASM / browsers etc)
https://github.com/kaspanet/rusty-kaspa/tree/tn12/wasm

metamask json-rpc
https://docs.metamask.io/services/reference/ethereum/json-rpc-methods/
metamask multichain
https://docs.metamask.io/tutorials/pnp-no-modal-multichain/

vprogs
https://github.com/kaspanet/vprogs/tree/feat/zk-preparations
