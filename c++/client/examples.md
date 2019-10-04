---
id: examples
title: Examples
---

# Examples

## Initialization

```cpp
Ark::Client::Connection<Ark::Client::Api> connection("my.node.ip.address", port);
```

## Blocks

This service API grants access to the [blocks resource](https://github.com/ArkEcosystem/gitbooks-sdk/tree/fcb399a02301c4ed91f0da34e9adbad8e0d2f3dc/api/public/v2/blocks.html). A block is a signed set of transactions created by a delegate and permanently committed to the ARK blockchain.

> It is not possible to `POST` a block through the public API. Relay Nodes accept only blocks posted by a delegate at the correct time through the internal API.

### List All Blocks

```cpp
const auto blocks = connection.api.blocks.all()

>>> std::string
```

### Retrieve a Block

```cpp
const auto block = connection.api.blocks.get("validBlockId")

>>> std::string
```

### List All Transactions of a Block

```cpp
const auto blockTransactionss = connection.api.blocks.transactions("validBlockId")

>>> std::string
```

### Search All Blocks

```cpp
const std::map<std::string, std::string> body = {
    { "id", "validBlockId" },
    { "previousBlock", "validBlockId" },
    { "version", "validVersion" }
};

const auto walletsSearch = connection.api.blocks.search(body);

>>> std::string
```

## Delegates

The client SDK can be used to query the [delegate resource](https://github.com/ArkEcosystem/gitbooks-sdk/tree/fcb399a02301c4ed91f0da34e9adbad8e0d2f3dc/api/public/v2/delegates.html).

A delegate is a regular wallet that has broadcasted a registration transaction, acquired a sufficient number of votes, and has a Relay Node configured to forge new blocks through a `forger` module. At any time only 51 delegates are active. They are cost-efficient miners running the ARK network.

> Voters are wallets which have broadcasted a vote transaction on a delegate. A vote remains active until an un-vote transaction is sent \(it does not have to be recast unless a wallet wishes to change from delegate\). Voting for a delegate does not give the delegate access to the wallet nor does it lock the coins in it.

### List All Delegates

```cpp
const auto delegates = connection.api.delegates.all();

>>> std::string
```

### Retrieve a Delegate

```cpp
const auto delegate = connection.api.delegates.get("validDelegateId");

>>> std::string
```

### List All Blocks of a Delegate

```cpp
const auto delegateBlocks = connection.api.delegates.blocks("validDelegateId");

>>> std::string
```

### List All Voters of a Delegate

```cpp
const auto delegateVoters = connection.api.delegates.voters("validDelegateId");

>>> std::string
```

## Node

The ARK network consists of different anonymous nodes \(servers\), maintaining the public ledger, validating transactions and blocks and providing APIs. The [node resource](https://github.com/ArkEcosystem/gitbooks-sdk/tree/fcb399a02301c4ed91f0da34e9adbad8e0d2f3dc/api/public/v2/node.html) allows for querying the health and configurations of the node used by the instantiated client.

### Retrieve the Configuration

```cpp
const auto nodeConfiguration = connection.api.node.configuration();

>>> std::string
```

### Retrieve the Status

```cpp
const auto nodeStatus = connection.api.node.status();

>>> std::string
```

### Retrieve the Syncing Status

```cpp
const auto nodeSyncing = connection.api.node.syncing();

>>> std::string
```

## Peers

Each node is connected to a set of peers, which are Relay or Delegate Nodes as well. The [peers resource](https://github.com/ArkEcosystem/gitbooks-sdk/tree/fcb399a02301c4ed91f0da34e9adbad8e0d2f3dc/api/public/v2/peers.html) provides access to all peers connected to our node.

> Peers have made their Public API available for use; however for mission-critical queries and transaction posting you should use a node which is under your control. We provide a guide to setting up a Relay Node [here](https://github.com/ArkEcosystem/gitbooks-sdk/tree/fcb399a02301c4ed91f0da34e9adbad8e0d2f3dc/tutorials/node/setup.html).

### List All Peers

```cpp
const auto peers = connection.api.peers.all();

>>> std::string
```

### Retrieve a Peer

```cpp
const auto peer = connection.api.peers.get("validIpAddress");

>>> std::string
```

## Transactions

The heart of any blockchain is formed by its transactions; state-altering payloads signed by a wallet. Most likely you will be querying for transactions most often, using the [transaction resource](https://github.com/ArkEcosystem/gitbooks-sdk/tree/fcb399a02301c4ed91f0da34e9adbad8e0d2f3dc/api/public/v2/transactions.html).

> A transaction is the only object which may be posted by a non-delegate. It requires a signature from a wallet containing a sufficient amount of ARK.

### Create a Transaction

```cpp
std::string jsonTransaction = "{" 
    "\"transactions\":["
        ...
    "]"
"}";

const auto transaction = connection.api.transactions.send(jsonTransaction);

>>> std::string
```

### Retrieve a Transaction

```cpp
const auto transaction = connection.api.transactions.get("validTransactionId");

>>> std::string
```

### List All Transactions

```cpp
const auto transactions = connection.api.transactions.all();

>>> std::string
```

### List All Unconfirmed Transactions

```cpp
const auto unconfirmedTransactions = connection.api.transactions.allUnconfirmed();

>>> std::string
```

### Get Unconfirmed Transaction

```cpp
const auto transactionUnconfirmed = connection.api.transactions.getUnconfirmed("validTransactionId");

>>> std::string
```

### Search Transactions

```cpp
const std::map<std::string, std::string> body = {
    { "height", "validHeight" }
};

const auto transactions = connection.api.transactions.search(body);

>>> std::string
```

### List Transaction Types

```cpp
const auto transactionTypes = connection.api.transactions.types();

>>> std::string
```

## Votes

A [vote](https://github.com/ArkEcosystem/gitbooks-sdk/tree/fcb399a02301c4ed91f0da34e9adbad8e0d2f3dc/api/public/v2/votes.html) is a transaction sub-type, where the `asset` field contains a `votes` object and the `transaction.type` is `3`.

### List All Votes

```cpp
const auto votes = connection.api.votes.all();

>>> std::string
```

### Retrieve a Vote

```cpp
const auto vote = connection.api.votes.get("validVoteId");

>>> std::string
```

## Wallets

The [wallet resource](https://github.com/ArkEcosystem/gitbooks-sdk/tree/fcb399a02301c4ed91f0da34e9adbad8e0d2f3dc/api/public/v2/wallets.html#list-all-wallets) provides access to:

* Wallets.
* Incoming and outgoing transactions per wallet.
* Each wallet's votes.

### Retrieve All Wallets

```cpp
const auto wallet = connection.api.wallets.all();

>>> std::string
```

### Retrieve a Wallet

```cpp
const auto wallet = connection.api.wallets.get("validWalletId");

>>> std::string
```

### List All Transactions of a Wallet

```cpp
const auto walletTransactions = connection.api.wallets.transactions("validAddress");

>>> std::string
```

### List All Received Transactions of a Wallet

```cpp
const auto walletTransactionsReceived = connection.api.wallets.transactionsReceived("validWalletAddress")

>>> std::string
```

### List All Sent Transactions of a Wallet

```cpp
const auto walletTransactionsSent = connection.api.wallets.transactionsSent("validWalletAddress")

>>> std::string
```

### List All Votes of a Wallet

```cpp
const auto walletVotes = connection.api.wallets.votes("validWalletAddress")

>>> std::string
```

### List All Top Wallets

```cpp
const auto walletsTop = connection.api.wallets.top();

>>> std::string
```

### Search All Wallets

```cpp
const std::map<std::string, std::string> body_parameters = {
    { "username", "validUsername" },
    { "address", "validAddress" },
    { "publicKey", "validPublicKey" }
};

const auto walletsSearch = connection.api.wallets.search(body_parameters);

>>> std::string
```

