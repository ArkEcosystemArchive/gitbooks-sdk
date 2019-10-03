---
id: api-documentation
title: API Documentation
---

## client.api.blocks.Blocks

### `all()`

```py
def all(self, page=None, limit=100, **kwargs)
```

List All Blocks.

#### Parameters

| Type | Name       | Required | Description      |
| ---- | ---------- | -------- | ---------------- |
| int  | page       | No       | Pagination       |
| int  | limit      | No       | Result limits    |
| any  | \*\*kwargs | No       | Query parameters |

#### Return Value

`<class 'dict'>`

---

### `get()`

```py
def get(self, block_id)
```

Retrieve a Block

#### Parameters

| Type | Name     | Required | Description |
| ---- | -------- | -------- | ----------- |
| int  | block_id | Yes      | Block ID    |

#### Return Value

`<class 'dict'>`

---

### `transactions()`

```py
def transactions(self, block_id, page=None, limit=100)
```

List All Transactions of a Block

#### Parameters

| Type | Name     | Required | Description      |
| ---- | -------- | -------- | ---------------- |
| str  | block_id | Yes      | Block ID         |
| int  | page     | No       | Pagination       |
| int  | limit    | No       | Query parameters |

#### Return Value

`<class 'dict'>`

---

### `search()`

```py
def search(self, criteria, page=None, limit=100)
```

Search All Blocks

#### Parameters

| Type | Name     | Required | Description       |
| ---- | -------- | -------- | ----------------- |
| dict | criteria | Yes      | Search parameters |
| int  | page     | No       | Pagination        |
| int  | limit    | No       | Result limit      |

#### Return Value

`<class 'dict'>`

## client.api.delegates.Delegates

### `all()`

```py
def all(self, page=None, limit=100, **kwargs)
```

List All Delegates

#### Parameters

| Type | Name       | Required | Description      |
| ---- | ---------- | -------- | ---------------- |
| int  | page       | No       | Pagination       |
| int  | limit      | No       | Result limits    |
| any  | \*\*kwargs | No       | Query parameters |

#### Return Value

`<class 'dict'>`

---

### `get()`

```py
def get(self, delegate_id)
```

Retrieve a Delegate

#### Parameters

| Type | Name        | Required | Description         |
| ---- | ----------- | -------- | ------------------- |
| int  | delegate_id | Yes      | Delegate identifier |

#### Return Value

`<class 'dict'>`

---

### `search()`

```py
def search(self, username, page=None, limit=100)
```

Search Delegates

#### Parameters

| Type | Name     | Required | Description       |
| ---- | -------- | -------- | ----------------- |
| str  | username | Yes      | Delegate username |
| int  | page     | No       | Pagination        |
| int  | limit    | No       | Result limits     |

#### Return Value

`<class 'dict'>`

---

### `blocks()`

```py
def blocks(self, delegate_id, page=None, limit=100)
```

List All Blocks of a Delegate

#### Parameters

| Type | Name        | Required | Description         |
| ---- | ----------- | -------- | ------------------- |
| str  | delegate_id | Yes      | Delegate identifier |
| int  | page        | No       | Pagination          |
| int  | limit       | No       | Result limits       |

#### Return Value

`<class 'dict'>`

---

### `voters()`

```py
def voters(self, delegate_id, page=None, limit=100, **kwargs)
```

List All Voters of a Delegate

#### Parameters

| Type | Name        | Required | Description         |
| ---- | ----------- | -------- | ------------------- |
| str  | delegate_id | Yes      | Delegate identifier |
| int  | page        | No       | Pagination          |
| int  | limit       | No       | Result limits       |
| any  | **kwargs    | No       | Query parameters    |

#### Return Value

`<class 'dict'>`

## client.api.node.Node

### `configuration()`

```py
def configuration(self)
```

Retrieve the Configuration

#### Return Value

`<class 'dict'>`

---

### `status()`

```py
def status(self)
```

Retrieve the Status

#### Return Value

`<class 'dict'>`

---

### `syncing()`

```py
def syncing(self)
```

Retrieve the Syncing Status

#### Return Value

`<class 'dict'>`

---

### `fees()`

```py
def fees(self, days=None)
```

Retrieve the Fees

#### Parameters

| Type | Name | Required | Description |
| ---- | ---- | -------- | ----------- |
| int  | days | No       | ...         |

#### Return Value

`<class 'dict'>`

## client.api.peers.Peers

### `all()`

```py
def all(self, os=None, status=None, port=None, version=None, order_by=None, page=None, limit=100)
```

List All Peers

#### Parameters

| Type | Name     | Required | Description      s|
| ---- | -------- | -------- | ---------------- |
| str  | os       | No       | Operating System |
| str  | status   | No       | Peer status      |
| int  | port     | No       | Peer port        |
| str  | version  | No       | Peer version     |
| str  | order_by | No       | Order by         |
| int  | page     | No       | Pagination       |
| int  | limit    | No       | Result limit     |

#### Return Value

`<class 'dict'>`

---

### `get()`

```py
def get(self, ip)
```

Retrieve a Peer

#### Parameters

| Type | Name | Required | Description |
| ---- | ---- | -------- | ----------- |
| str  | ip   | Yes      | IP addresss  |

#### Return Value

`<class 'dict'>`

## client.api.transactions.Transactions

### `create()`

```py
def create(self, transactions)
```

Create a Transaction

#### Parameters

| Type | Name         | Required | Description              |
| ---- | ------------ | -------- | ------------------------ |
| list | transactions | Yes      | Transaction to broadcast |

#### Return Value

`<class 'dict'>`

---

### `get()`

```py
def get(self, transaction_id)
```

Retrieve a Transaction

#### Parameters

| Type | Name           | Required | Description    |
| ---- | -------------- | -------- | -------------- |
| str  | transaction_id | Yes      | Transaction ID |

#### Return Value

`<class 'dict'>`

---

### `all()`

```py
def all(self, page=None, limit=100, **kwargs)
```

List All Transactions

#### Parameters

| Type | Name       | Required | Description      |
| ---- | ---------- | -------- | ---------------- |
| int  | page       | No       | Pagination       |
| int  | limit      | No       | Result limit     |
| any  | \*\*kwargs | No       | Query parameters |

#### Return Value

`<class 'dict'>`

---

### `all_unconfirmed()`

```py
def all_unconfirmed(self, limit=100, offset=None, **kwargs)
```

List All Unconfirmed Transactions

#### Parameters

| Type | Name       | Required | Description      |
| ---- | ---------- | -------- | ---------------- |
| int  | limit      | No       | Result limit     |
| int  | offset     | No       | Offset           |
| any  | \*\*kwargs | No       | Query parameters |

#### Return Value

`<class 'dict'>`

---

### `get_unconfirmed()`

```py
def get_unconfirmed(self, transaction_id)
```

Get Unconfirmed Transaction

#### Parameters

| Type | Name           | Required | Description    |
| ---- | -------------- | -------- | -------------- |
| str  | transaction_id | Yes      | Transaction ID |

#### Return Value

`<class 'dict'>`

---

### `search()`

```py
def search(self, criteria, page=None, limit=100)
```

Search Transactions

#### Parameters

| Type | Name     | Required | Description       |
| ---- | -------- | -------- | ----------------- |
| dict | criteria | Yes      | Search parameters |
| int  | page     | No       | Pagination        |
| int  | limit    | No       | Result limit      |

#### Return Value

`<class 'dict'>`

---

### `types()`

```py
def types(self)
```

List Transaction Types

#### Return Value

`<class 'dict'>`

---

### `fees()`

```py
def fees(self)
```

List Transaction Fees (Non-Dynamic)

#### Return Value

`<class 'dict'>`

## client.api.votes.Votes

### `all()`

```py
def all(self, page=None, limit=100)
```

List All Votes

#### Parameters

| Type | Name     | Required | Description  s|
| ---- | -------- | -------- | ------------ |
| int  | page     | No       | Pagination   |
| int  | limit    | No       | Result limit |

#### Return Value

`<class 'dict'>`

---

### `get()`

```py
def get(self, vote_id)
```

Retrieve a Vote

#### Parameters

| Type | Name     | Required | Description |
| ---- | -------- | -------- | ----------- |
| str  | vote_id  | Yes      | Vote IDs     |

#### Return Value

`<class 'dict'>`

## client.api.wallets.Wallets

### `all()`

```py
def all(self, page=None, limit=100)
```

Retrieve All Wallets

#### Parameters

| Type | Name     | Required | Description  |
| ---- | -------- | -------- | ------------ |
| int  | page     | No       | Pagination   |
| int  | limit    | No       | Result limit |

#### Return Value

`<class 'dict'>`

---

### `get()`

```py
def get(self, wallet_id)
```

Retrieve a Wallet

#### Parameters

| Type | Name      | Required | Description       |
| ---- | --------- | -------- | ----------------- |
| str  | wallet_id | Yes      | Wallet identifier |

#### Return Value

`<class 'dict'>`

---

### `transactions()`

```py
def transactions(self, wallet_id ,page=None, limit=100, **kwargs)
```

List All Transactions of a Wallet

#### Parameters

| Type | Name       | Required | Description       |
| ---- | ---------- | -------- | ----------------- |
| str  | wallet_id  | Yes      | Wallet identifier |
| int  | page       | No       | Pagination        |
| int  | limit      | No       | Result limit      |
| any  | \*\*kwargs | No       | Query parameters  |

#### Return Value

`<class 'dict'>`

---

### `transactions_received()`

```py
def transactions_received(self, wallet_id, page=None, limit=100)
```

List All Received Transactions of a Wallet

#### Parameters

| Type | Name       | Required | Description       |
| ---- | ---------- | -------- | ----------------- |
| str  | wallet_id  | Yes      | Wallet identifier |
| int  | page       | No       | Pagination        |
| int  | limit      | No       | Result limit      |

#### Return Value

`<class 'dict'>`

---

### `transactions_sent()`

```py
def transactions_sent(self, wallet_id, page=None, limit=100)
```

List All Sent Transactions of a Wallet

#### Parameters

| Type | Name       | Required | Description       |
| ---- | ---------- | -------- | ----------------- |
| str  | wallet_id  | Yes      | Wallet identifier |
| int  | page       | No       | Pagination        |
| int  | limit      | No       | Result limit      |

#### Return Value

`<class 'dict'>`

---

### `votes()`

```py
def votes(self, wallet_id,page=None, limit=100)
```

List All Votes of a Wallet

#### Parameters

| Type | Name       | Required | Description       |
| ---- | ---------- | -------- | ----------------- |
| str  | wallet_id  | Yes      | Wallet identifier |
| int  | page       | No       | Pagination        |
| int  | limit      | No       | Result limit      |

#### Return Value

`<class 'dict'>`

---

### `top()`

```py
def top(self, page=None, limit=100)
```

List All Top Wallets

#### Parameters

| Type | Name       | Required | Description       |
| ---- | ---------- | -------- | ----------------- |
| int  | page       | No       | Pagination        |
| int  | limit      | No       | Result limit      |

#### Return Value

`<class 'dict'>`

---

### `search()`

```py
def search(self, criteria, page=None, limit=100)
```

Search All Wallets

#### Parameters

| Type | Name      | Required | Description       |
| ---- | --------- | -------- | ----------------- |
| dict | criteria  | Yes      | Search parameters |
| int  | page      | No       | Pagination        |
| int  | limit     | No       | Result limit      |

#### Return Value

`<class 'dict'>`
