---
id: examples
title: Examples
---

## Initialization

```ts
import ApiClient from '@arkecosystem/client'

const client = new ApiClient(server, 2) // API version
```

## Blocks

This service API grants access to the [blocks resource](/api/public/v2/blocks.html). A block is a signed set of transactions created by a delegate and permanently committed to the ARK blockchain.

> It is not possible to `POST` a block through the public API. Relay Nodes accept only blocks posted by a delegate at the correct time through the internal API.

### List All Blocks

```ts
const { blocks } = await client.resource('blocks').all()

>>> Promise<IResponse<T>>
```

### Retrieve a Block

```ts
const { block } = await client.resource('blocks').get('validBlockId')

>>> Promise<IResponse<T>>
```

### List All Transactions of a Block

```ts
const { blockTransactions } = await client.resource('blocks').transactions('validBlockId')

>>> Promise<IResponse<T>>
```

### Search All Blocks

```ts
const { searchedBlocks } = await client.resource('blocks').search({"id": "validBlockId"})

>>> Promise<IResponse<T>>
```

## Delegates

The client SDK can be used to query the [delegate resource](/api/public/v2/delegates.html).

A delegate is a regular wallet that has broadcasted a registration transaction, acquired a sufficient number of votes, and has a Relay Node configured to forge new blocks through a `forger` module. At any time only 51 delegates are active. They are cost-efficient miners running the ARK network.

> Voters are wallets which have broadcasted a vote transaction on a delegate. A vote remains active until an un-vote transaction is sent (it does not have to be recast unless a wallet wishes to change from delegate). Voting for a delegate does not give the delegate access to the wallet nor does it lock the coins in it.

### List All Delegates

```ts

const { delegates } = await client.resource('delegates').all()

>>> Promise<IResponse<T>>
```

### Retrieve a Delegate

```ts
const { delegate } = await client.resource('delegates').get("validId")

>>> Promise<IResponse<T>>
```

### List All Blocks of a Delegate

```ts
const { delegateBlocks } = await client.resource('delegates').blocks("validId")

>>> Promise<IResponse<T>>
```

### List All Voters of a Delegate

```ts
const { delegateVoters } = await client.resource('delegates').voters("validId")

>>> Promise<IResponse<T>>
```

## Node

The ARK network consists of different anonymous nodes (servers), maintaining the public ledger, validating transactions and blocks and providing APIs. The [node resource](/api/public/v2/node.html) allows for querying the health and configurations of the node used by the instantiated client.

### Retrieve the Configuration

```ts
const { nodeConfiguration } = await client.resource('node').configuration()

>>> Promise<IResponse<T>>
```

### Retrieve the Status

```ts
const { nodeStatus } = await client.resource('node').status()

>>> Promise<IResponse<T>>
```

### Retrieve the Syncing Status

```ts
const { nodeSyncing } = await client.resource('node').syncing()

>>> Promise<IResponse<T>>
```

### Retrieve the Fees

```ts
const { nodeFees } = await client.resource('node').fees()

>>> Promise<IResponse<T>>
```

## Peers

Each node is connected to a set of peers, which are Relay or Delegate Nodes as well. The [peers resource](/api/public/v2/peers.html) provides access to all peers connected to our node.

> Peers have made their Public API available for use; however for mission-critical queries and transaction posting you should use a node which is under your control. We provide a guide to setting up a Relay Node [here](/tutorials/node/setup.html).

### List All Peers

```ts
const { peers } = await client.resource('peers').all()

>>> Promise<IResponse<T>>
```

### Retrieve a Peer

```ts
const { peer } = await client.resource('peers').get("validIpAddress")

>>> Promise<IResponse<T>>
```

## Transactions

The heart of any blockchain is formed by its transactions; state-altering payloads signed by a wallet. Most likely you will be querying for transactions most often, using the [transaction resource](/api/public/v2/transactions.html).

> A transaction is the only object which may be posted by a non-delegate. It requires a signature from a wallet containing a sufficient amount of ARK.

### Create a Transaction

```ts
const { transaction } = await client.resource('transactions').create([...])

>>> Promise<IResponse<T>>
```

### Retrieve a Transaction

```ts
const { transaction } = await client.resource('transactions').get("validId")

>>> Promise<IResponse<T>>
```

### List All Transactions

```ts
const { transaction } = await client.resource('transactions').all()

>>> Promise<IResponse<T>>
```

### List All Unconfirmed Transactions

```ts
const { transaction } = await client.resource('transactions').allUnconfirmed()

>>> Promise<IResponse<T>>
```

### Get Unconfirmed Transaction

```ts
const { transaction } = await client.resource('transactions').getUnconfirmed("validId")

>>> Promise<IResponse<T>>
```

### Search Transactions

```ts
const { transaction } = await client.resource('transactions').search({"id": "validId"})

>>> Promise<IResponse<T>>
```

### List Transaction Types

```ts
const { transaction } = await client.resource('transactions').types()

>>> Promise<IResponse<T>>
```

## Votes

A [vote](/api/public/v2/votes.html) is a transaction sub-type, where the `asset` field contains a `votes` object and the `transaction.type` is `3`.

### List All Votes

```ts
const { votes } = await client.resource('votes').all()

>>> Promise<IResponse<T>>
```

### Retrieve a Vote

```ts
const { vote } = await client.resource('votes').get("validId")

>>> Promise<IResponse<T>>
```

## Wallets

The [wallet resource](/api/public/v2/wallets.html#list-all-wallets) provides access to:

- Wallets.
- Incoming and outgoing transactions per wallet.
- Each wallet's votes.

### Retrieve All Wallets

```ts
const { wallets } = await client.resource('wallets').all()

>>> Promise<IResponse<T>>
```

### Retrieve a Wallet

```ts
const { wallet } = await client.resource('wallets').get("validId")

>>> Promise<IResponse<T>>
```

### List All Transactions of a Wallet

```ts
const { walletTransactions } = await client.resource('wallets').transactions("validId")

>>> Promise<IResponse<T>>
```

### List All Received Transactions of a Wallet

```ts
const { wallets } = await client.resource('wallets').transactionsReceived("validId")

>>> Promise<IResponse<T>>
```

### List All Sent Transactions of a Wallet

```ts
const { wallets } = await client.resource('wallets').transactionsSent("validId")

>>> Promise<IResponse<T>>
```

### List All Votes of a Wallet

```ts
const { wallets } = await client.resource('wallets').votes("validId")

>>> Promise<IResponse<T>>
```

### List All Top Wallets

```ts
const { wallets } = await client.resource('wallets').top()

>>> Promise<IResponse<T>>
```

### Search All Wallets

```ts
const { wallets } = await client.resource('wallets').search({"id": "validId"})

>>> Promise<IResponse<T>>
```