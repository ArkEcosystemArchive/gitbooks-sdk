---
id: api-documentation
title: API Documentation
---

## Ark::Client::API::Blocks

### `all()`

```cpp
std::string Ark::Client::API::Blocks::all(
    int limit /* = 5 */,
    int page /* = 1 */)
```

Get all blocks.

#### Parameters

| Type  | Name       | Required | Description      |
| ----- | ---------- | -------- | ---------------- |
| int   | limit      | No       | Limit of results |
| int   | page       | No       | Pagination       |


#### Return Value

`std::string`

---

### `get()`

```cpp
std::string Ark::Client::API::Blocks::get(
    const char *const blockId)
```

Get a block by the given id.

#### Parameters

| Type   | Name     | Required | Description |
| ------ | -------- | -------- | ----------- |
| char   | blockID  | Yes      | Block ID    |

#### Return Value

`std::string`

---

### `transactions()`

```cpp
std::string Ark::Client::API::Blocks::transactions(
    const char *const blockId)
```

Get all transactions by the given block.

#### Parameters

| Type   | Name    | Required | Description |
| ------ | ------- | -------- | ----------- |
| char   | blockId | Yes      | Block ID    |

#### Return Value

`std::string`

---

### `search()`

```cpp
std::string Ark::Client::API::Blocks::search(
    const std::map<std::string, std::string> &bodyParameters,
    int limit /* = 5 */,
    int page /* = 1 */)
```

Filter all blocks by the given parameters.

#### Parameters

| Type                               | Name            | Required | Description       |
| ---------------------------------- | --------------- | -------- | ----------------- |
| std::map<std::string, std::string> | &bodyParameters | Yes      | Search Parameters |
| int                                | limit           | No       | Limit of results  |
| int                                | page            | No       | Pagination        |

#### Return Value

`std::string`

## Ark::Client::API::Delegates

### `all()`

```cpp
std::string Ark::Client::API::Delegates::all(
    int limit /* = 5 */,
    int page /* = 1 */)
```

Get all accounts.

#### Parameters

| Type  | Name       | Required | Description      |
| ----- | ---------- | -------- | ---------------- |
| int   | limit      | No       | Limit of results |
| int   | page       | No       | Pagination       |

#### Return Value

`std::string`

---

### `get()`

```cpp
std::string Ark::Client::API::Delegates::get(
    const char *const identifier)
```

Get a delegate by the given id.

#### Parameters

| Type   | Name       | Required | Description         |
| ------ | ---------- | -------- | ------------------- |
| char   | identifier | Yes      | Delegate identifier |

#### Return Value

`std::string`

---

### `blocks()`

```cpp
std::string Ark::Client::API::Delegates::blocks(
    const char *const identifier,
    int limit /* = 5 */,
    int page /* = 1 */)
```

Get all blocks for the given delegate.

#### Parameters

| Type  | Name       | Required | Description         |
| ----- | ---------- | -------- | ------------------- |
| char  | identfier  | Yes      | Delegate identifier |
| int   | limit      | No       | Limit of results    |
| int   | page       | No       | Pagination          |

#### Return Value

`std::string`

---

### `voters()`

```cpp
std::string Ark::Client::API::Delegates::voters(
    const char *const identifier,
    int limit /* = 5 */,
    int page /* = 1 */)
```

Get all voters for the given delegate.

#### Parameters

| Type  | Name       | Required | Description         |
| ----- | ---------- | -------- | ------------------- |
| char  | identfier  | Yes      | Delegate identifier |
| int   | limit      | No       | Limit of results    |
| int   | page       | No       | Pagination          |

#### Return Value

`std::string`

## Ark::Client::API::Node

### `configuration()`

```cpp
std::string Ark::Client::API::Node::configuration()
```

Get the node configuration.

#### Return Value

`std::string`

---

### `status()`

```cpp
std::string Ark::Client::API::Node::status()
```

Get the node status.

#### Return Value

`std::string`

---

### `syncing()`

```cpp
std::string Ark::Client::API::Node::syncing()
```

Get the node syncing status.

#### Return Value

`std::string`

## Ark::Client::API::Peers

### `all()`

```cpp
std::string Ark::Client::API::Peers::all(
    int limit /* = 5 */,
    int page /* = 1 */
)
```

Get all peers.

#### Parameters

| Type  | Name       | Required | Description      |
| ----- | ---------- | -------- | ---------------- |
| int   | limit      | No       | Limit of results |
| int   | page       | No       | Pagination       |

#### Return Value

`std::string`

---

### `get()`

```cpp
std::string Ark::Client::API::Peers::get(
    const char *const ip)
```

Get a peer by the given IP address.

#### Parameters

| Type   | Name | Required | Description |
| ------ | ---- | -------- | ----------- |
| char   | ip   | Yes      | IP address  |

#### Return Value

`std::string`

## Ark::Client::API::Transactions

### `send()`

```cpp
std::string Ark::Client::API::Transactions::send(
    std::string& jsonTransaction)
```

Create a new transaction.

#### Parameters

| Type         | Name            | Required | Description |
| ------------ | --------------- | -------- | ----------- |
| std::string& | jsonTransaction | Yes      | Transaction |

#### Return Value

`std::string`

---

### `get()`

```cpp
std::string Ark::Client::API::Transactions::get(
    const char *const identifier)
```

Get a transaction by the given id.

#### Parameters

| Type   | Name       | Required | Description    |
| ------ | ---------- | -------- | -------------- |
| char   | identifier | Yes      | Transaction ID |

#### Return Value

`std::string`

---

### `all()`

```cpp
std::string Ark::Client::API::Transactions::all(
    int limit /* = 5 */,
    int page /* = 1 */)
```

Get all transactions.

#### Parameters

| Type  | Name       | Required | Description      |
| ----- | ---------- | -------- | ---------------- |
| int   | limit      | No       | Limit of results |
| int   | page       | No       | Pagination       |

#### Return Value

`std::string`

---

### `allUnconfirmed()`

```cpp
std::string Ark::Client::API::Transactions::allUnconfirmed(
    int limit /* = 5 */,
    int page /* =1 */)
```

Get all unconfirmed transactions.

#### Parameters

| Type  | Name       | Required | Description      |
| ----- | ---------- | -------- | ---------------- |
| int   | limit      | No       | Limit of results |
| int   | page       | No       | Pagination       |

#### Return Value

`std::string`

---

### `getUnconfirmed()`

```cpp
std::string Ark::Client::API::Transactions::getUnconfirmed(
    const char *const identifier)
```

Get an unconfirmed transaction by the given id.

#### Parameters

| Type   | Name       | Required | Description    |
| ------ | ---------- | -------- | -------------- |
| char   | identifier | Yes      | Transaction ID |

#### Return Value

`std::string`

---

### `search()`

```cpp
std::string Ark::Client::API::Transactions::search(
    const std::map<std::string, std::string> &bodyParameters,
    int limit /* = 5 */,
    int page /* = 1 */)
```

Filter all transactions by the given parameters.

#### Parameters

| Type                               | Name            | Required | Description       |
| ---------------------------------- | --------------- | -------- | ----------------- |
| std::map<std::string, std::string> | &bodyParameters | Yes      | Search parameters |
| int                                | limit           | No       | Limit of results  |
| int                                | page            | No       | Pagination        |

#### Return Value

`std::string`

---

### `types()`

```cpp
std::string Ark::Client::API::Transactions::types()
```

Get a list of valid transaction types.

#### Return Value

`std::string`

## Ark::Client::API::Votes

### `all()`

```cpp
std::string Ark::Client::API::Votes::all(
    int limit /* = 5 */,
    int page /* = 1 */)
```

Get all votes.

#### Parameters

| Type  | Name       | Required | Description      |
| ----- | ---------- | -------- | ---------------- |
| int   | limit      | No       | Limit of results |
| int   | page       | No       | Pagination       |

#### Return Value

`std::string`

---

### `get()`

```cpp
std::string Ark::Client::API::Votes::get(
    const char *const identifier)
```

Get a vote by the given id.

#### Parameters

| Type   | Name       | Required | Description |
| ------ | ---------- | -------- | ----------- |
| char   | identifier | Yes      | Vote ID     |

#### Return Value

`std::string`

## Ark::Client::API::Wallets 

### `all()`

```cpp
std::string Ark::Client::API::Wallets::all(
    int limit /* = 5 */,
    int page /* = 1 */)
```

Get all wallets.

#### Parameters

| Type  | Name       | Required | Description      |
| ----- | ---------- | -------- | ---------------- |
| int   | limit      | No       | Limit of results |
| int   | page       | No       | Pagination       |

#### Return Value

`std::string`

---

### `get()`

```cpp
std::string Ark::Client::API::Wallets::get(
    const char *const identifier)
```

Get a wallet by the given id.

#### Parameters

| Type   | Name       | Required | Description |
| ------ | ---------- | -------- | ----------- |
| char   | identifier | Yes      | Wallet ID   |

#### Return Value

`std::string`

---

### `transactions()`

```cpp
std::string Ark::Client::API::Wallets::transactions(
    const char *const identifier,
    int limit /* = 5 */,
    int page /* = 1 */)
```

Get all transactions for the given wallet.

#### Parameters

| Type  | Name       | Required | Description       |
| ----- | ---------- | -------- | ----------------- |
| char  | identifier | No       | Wallet identifier |
| int   | limit      | No       | Limit of results  |
| int   | page       | No       | Pagination        |

#### Return Value

`std::string`

---

### `transactionsReceived()`

```cpp
std::string Ark::Client::API::Wallets::transactionsReceived(
    const char *const identifier,
    int limit /* = 5 */,
    int page /* = 1 */)
```

Get all transactions received by the given wallet.

#### Parameters

| Type  | Name       | Required | Description       |
| ----- | ---------- | -------- | ----------------- |
| char  | identifier | No       | Wallet identifier |
| int   | limit      | No       | Limit of results  |
| int   | page       | No       | Pagination        |

#### Return Value

`std::string`

---

### `transactionsSent()`

```cpp
std::string Ark::Client::API::Wallets::transactionsSent(
    const char *const identifier,
    int limit /* = 5 */,
    int page /* = 1 */)
```

Get all transactions sent by the given wallet.

#### Parameters

| Type  | Name       | Required | Description       |
| ----- | ---------- | -------- | ----------------- |
| char  | identifier | No       | Wallet identifier |
| int   | limit      | No       | Limit of results  |
| int   | page       | No       | Pagination        |

#### Return Value

`std::string`

---

### `votes()`

```cpp
std::string Ark::Client::API::Wallets::votes(
    const char *const identifier,
    int limit /* = 5 */,
    int page /* = 1 */)
```

Get all votes by the given wallet.

#### Parameters

| Type  | Name       | Required | Description       |
| ----- | ---------- | -------- | ----------------- |
| char  | identifier | No       | Wallet identifier |
| int   | limit      | No       | Limit of results  |
| int   | page       | No       | Pagination        |

#### Return Value

`std::string`

---

### `top()`

```cpp
std::string Ark::Client::API::Wallets::top(
    int limit /* = 5 */,
    int page /* = 1 */)
```

Get all wallets sorted by balance in descending order.

#### Parameters

| Type  | Name       | Required | Description       |
| ----- | ---------- | -------- | ----------------- |
| int   | limit      | No       | Limit of results  |
| int   | page       | No       | Pagination        |

#### Return Value

`std::string`

---

### `search()`

```cpp
std::string Ark::Client::API::Wallets::search(
    const std::map<std::string, std::string> &bodyParameters,
    int limit /* = 5 */,
    int page /* = 1 */)
```

Filter all wallets by the given parameters.

#### Parameters

| Type                               | Name            | Required | Description       |
| ---------------------------------- | --------------- | -------- | ----------------- |
| std::map<std::string, std::string> | &bodyParameters | Yes      | Search parameters |
| int                                | limit           | No       | Result limit      |
| int                                | page            | No       | Pagination        |

#### Return Value

`std::string`