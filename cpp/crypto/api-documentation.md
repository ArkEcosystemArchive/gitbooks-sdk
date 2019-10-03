---
id: api-documentation
title: API Documentation
---

## Ark::Crypto::Configuration::Fee

### `get()`


```cpp
uint64_t Ark::Crypto::Configuration::Fee::get(int type)
```

Get a fee for a given transaction type

#### Parameters

| Type | Name | Required | Description                                     |
| ---- | ---- | -------- | ----------------------------------------------- |
| int  | type | Yes      | Transaction type for which we wish to get a fee |


#### Return Value

`uint64_t`

---

### `set()`

```cpp
void Ark::Crypto::Configuration::Fee::set(int type, uint64_t fee)
```

Set a fee

#### Parameters

| Type     | Name | Required | Description                                     |
| -------- | ---- | -------- | ----------------------------------------------- |
| int      | type | Yes      | Transaction type for which we wish to set a fee |
| uint64_t | fee  | Yes      | Fee for a given transaction type                |

#### Return Value

`void`

## Ark::Crypto::Configuration::Network

### `set()`

```cpp
void Ark::Crypto::Configuration::Network::set(const Ark::Crypto::Networks::AbstractNetwork& network)
```

Set what network you want to use in the crypto library

#### Parameters

| Type             | Name    | Required | Description              |
| ---------------- | --------| -------- | ------------------------ |
| AbstractNetwork& | network | Yes      | Testnet, Devnet, Mainnet |

#### Return Value

`void`

---

### `get()`

```cpp
Ark::Crypto::Networks::AbstractNetwork Ark::Crypto::Configuration::Network::get()
```

Get settings for a selected network, default network is devnet

#### Return Value

`Ark::Crypto::Networks::AbstractNetwork`

## Ark::Crypto::Identities::Address

### `Address()`

```cpp
Ark::Crypto::Identities::Address::Address(const char *const newAddressStr)
```

Constructor of the Address class.

#### Parameters

| Type   | Name             | Required | Description            |
| ------ | ---------------- | -------- | ---------------------- |
| char   | newAddressStr    | Yes      | Valid address string   |

---

### `Address()`

```cpp
Ark::Crypto::Identities::Address::Address(const uint8_t *newAddressBytes)
```

Constructor of the Address class.

#### Parameters

| Type    | Name             | Required | Description            |
| ------- | ---------------- | -------- | ---------------------- |
| uint8_t | newAddressBytes  | Yes      | Valid address bytes    |

---

### `toBytes()`

```cpp
const uint8_t *Ark::Crypto::Identities::Address::toBytes()
```

Convert the address to its bytes representation.

#### Return Value

`uint8_t`

---

### `toString()`

```cpp
std::string Ark::Crypto::Identities::Address::toString()
```

Convert the address to its string representation.

#### Return Value

`std::string`

---

### `fromPublicKey()`

```cpp
Ark::Crypto::Identities::Address Ark::Crypto::Identities::Address::fromPublicKey(PublicKey publicKey,
                                                                                 uint8_t networkVersion)
```

Derive the address from the given public key.

#### Parameters

| Type            | Name             | Required | Description            |
| --------------- | ---------------- | -------- | ---------------------- |
| PublicKey       | publicKey        | Yes      | Public key             |
| uint8_t         | networkVersion   | Yes      | Version of the network |

#### Return Value

`Ark::Crypto::Identities::Address`

---

### `fromPrivateKey()`

```cpp
Ark::Crypto::Identities::Address Ark::Crypto::Identities::Address::fromPrivateKey(PrivateKey privateKey,
                                                                                  uint8_t networkVersion)
```

Derive the address from the given private key.

#### Parameters

| Type            | Name             | Required | Description            |
| --------------- | ---------------- | -------- | ---------------------- |
| PrivateKey      | privateKey       | Yes      | Private key            |
| uint8_t         | networkVersion   | Yes      | Version of the network |

#### Return Value

`Ark::Crypto::Identities::Address`

---

### `fromPassphrase()`

```cpp
Ark::Crypto::Identities::Address Ark::Crypto::Identities::Address::fromPassphrase(const char *const passphrase,
                                                                                  uint8_t networkVersion)
```

Derive the address from the given passphrase.

#### Parameters

| Type            | Name             | Required | Description            |
| --------------- | ---------------- | -------- | ---------------------- |
| char            | passphrase       | Yes      | Private key            |
| uint8_t         | networkVersion   | Yes      | Version of the network |

#### Return Value

`Ark::Crypto::Identities::Address`

---

### `validate()`

```cpp
bool Ark::Crypto::Identities::Address::validate(Address address, uint8_t networkVersion)
```

Validate the given address.

#### Parameters

| Type    | Name             | Required | Description            |
| ------- | ---------------- | -------- | ---------------------- |
| Address | address          | Yes      | Address to validate    |
| uint8_t | networkVersion   | Yes      | Version of the network |

#### Return Value

`bool`

---

### `validate()`

```cpp
bool Ark::Crypto::Identities::Address::validate(const char *const addressStr, uint8_t networkVersion)
```

Validate the given Address string to the network version.

#### Parameters

| Type    | Name             | Required | Description            |
| ------- | ---------------- | -------- | ---------------------- |
| char    | addressStr       | Yes      | Address to validate    |
| uint8_t | networkVersion   | Yes      | Version of the network |

#### Return Value

`bool`

---

### `validate()`

```cpp
bool Ark::Crypto::Identities::Address::validate(const uint8_t *addressBytes, uint8_t networkVersion)
```

Validate the given Address bytes to the network version.

#### Parameters

| Type    | Name             | Required | Description            |
| ------- | ---------------- | -------- | ---------------------- |
| uint8_t | *addressBytes    | Yes      | Address to validate    |
| uint8_t | networkVersion   | Yes      | Version of the network |

#### Return Value

`bool`

---

### `base58encode()`

```cpp
std::string Ark::Crypto::Identities::Address::base58encode(const uint8_t *source)
```

Reads 21 bytes from source and returns an base58 encoded string.

#### Parameters

| Type    | Name    | Required | Description            |
| ------- | ------- | -------- | ---------------------- |
| uint8_t | *source | Yes      | Bytes source           |

#### Return Value

`std::string`

---

### `bytesFromBase58Check()`

```cpp
std::vector<uint8_t> Ark::Crypto::Identities::Address::bytesFromBase58Check(const char *const address)
```

Reads 21 bytes from source and returns an base58 encoded string.

#### Parameters

| Type    | Name    | Required | Description            |
| ------- | ------- | -------- | ---------------------- |
| char    | address | Yes      | Valid address          |

#### Return Value

`std::vector<uint8_t>`

## Ark::Crypto::Identities::PrivateKey

### `PrivateKey()`

```cpp
Ark::Crypto::Identities::PrivateKey::PrivateKey(const char *const newPrivateKeyStr)
```

Constructor of the Private Key class.

#### Parameters

| Type     | Name             | Required | Description |
| -------- | ---------------- | -------- | ----------- |
| char     | newPrivateKeyStr | Yes      | Private Key |

---

### `PrivateKey()`

```cpp
Ark::Crypto::Identities::PrivateKey::PrivateKey(const uint8_t *newPrivateKeyBytes)
```

Constructor of the Private Key class.

#### Parameters

| Type     | Name                | Required | Description |
| -------- | ------------------- | -------- | ----------- |
| uint8_t  | *newPrivateKeyBytes | Yes      | Private Key |

---

### `toBytes()`

```cpp
const uint8_t *Ark::Crypto::Identities::PrivateKey::toBytes()
```

Convert the private key to its bytes representation.

#### Return Value

`uint8_t`

---

### `toString()`

```cpp
std::string Ark::Crypto::Identities::PrivateKey::toString()
```

Convert the private key to its string representation.

#### Return Value

`std::string`

---

### `fromPassphrase()`

```cpp
Ark::Crypto::Identities::PrivateKey Ark::Crypto::Identities::PrivateKey::fromPassphrase(const char *const passphrase)
```

Derive the private key for the given passphrase.

#### Parameters

| Type     | Name             | Required | Description |
| -------- | ---------------- | -------- | ----------- |
| char     | passphrase       | Yes      | Passphrase  |

#### Return Value

`Ark::Crypto::Identities::PrivateKey`

---

### `fromHex()`

```cpp
Ark::Crypto::Identities::PrivateKey Ark::Crypto::Identities::PrivateKey::fromHex(const char *const privateKey)
```

Create a private key instance from a hex string.

#### Parameters

| Type     | Name             | Required | Description |
| -------- | ---------------- | -------- | ----------- |
| char     | privateKey       | Yes      | Private key |

#### Return Value

`Ark::Crypto::Identities::PrivateKey`

---

### `fromWif()`

```cpp
Ark::Crypto::Identities::PrivateKey Ark::Crypto::Identities::PrivateKey::fromWIFString(const char *wifStr,
                                                                                       uint8_t wifByte)
```

Create a private key instance from the given WIF.

#### Parameters

| Type    | Name    | Required | Description        |
| ------- | ------- | -------- | ------------------ |
| char    | *wifStr | Yes      | Network WIF string |
| uint8_t | wifByte | Yes      | Network WIF bytes  |

#### Return Value

`Ark::Crypto::Identities::PrivateKey`

---

### `validate()`

```cpp
bool Ark::Crypto::Identities::PrivateKey::validate(PrivateKey privateKey)
```

Validate the given private key.

#### Parameters

| Type       | Name       | Required | Description |
| ---------- | ---------- | -------- | ----------- |
| PrivateKey | privateKey | Yes      | Private key |

#### Return Value

`bool`

---

### `validate()`

```cpp
bool Ark::Crypto::Identities::PrivateKey::validate(const char *privateKeyStr)
```

Validate the given private key.

#### Parameters

| Type | Name           | Required | Description        |
| ---- | -------------- | -------- | ------------------ |
| char | *privateKeyStr | Yes      | Private key string |

#### Return Value

`bool`

---

### `validate()`

```cpp
bool Ark::Crypto::Identities::PrivateKey::validate(const uint8_t *privateKeyBytes)
```

Validate the given private key.

#### Parameters

| Type    | Name             | Required | Description       |
| ------- | ---------------- | -------- | ----------------- |
| uint8_t | *privateKeyBytes | Yes      | Private key bytes |

#### Return Value

`bool`

## Ark::Crypto::Identities::PublicKey

### `PublicKey()`

```cpp
Ark::Crypto::Identities::PublicKey::PublicKey(const char *const newPublicKeyStr)
```

Constructor of the Public Key class.

#### Parameters

| Type     | Name             | Required | Description       |
| -------- | ---------------- | -------- | ----------------- |
| char     | newPublicKeyStr  | Yes      | Public key string |

---

### `PublicKey()`

```cpp
Ark::Crypto::Identities::PublicKey::PublicKey(const uint8_t *newPublicKeyBytes)
```

Constructor of the Public Key class.

#### Parameters

| Type     | Name               | Required | Description      |
| -------- | ------------------ | -------- | ---------------- |
| char     | *newPublicKeyBytes | Yes      | Public key bytes |

---

### `toBytes()`

```cpp
const uint8_t *Ark::Crypto::Identities::PublicKey::toBytes()
```

Convert the private key to its bytes representation.

#### Return Value

`uint8_t`

---

### `isValid()`

```cpp
bool Ark::Crypto::Identities::PublicKey::isValid()
```

Determine if the given public key is valid.

#### Return Value

`bool`

---

### `toString()`

```cpp
std::string Ark::Crypto::Identities::PublicKey::toString()
```

Convert the private key to its string representation.

#### Return Value

`std::string`

---

### `fromPassphrase()`

```cpp
Ark::Crypto::Identities::PublicKey Ark::Crypto::Identities::PublicKey::fromPassphrase(const char *const passphrase)
```

Derive the public from the given passphrase.

#### Parameters

| Type     | Name             | Required | Description |
| -------- | ---------------- | -------- | ----------- |
| char     | passphrase       | Yes      | Passphrase  |

#### Return Value

`Ark::Crypto::Identities::PublicKey`

---

### `fromPrivateKey()`

```cpp
Ark::Crypto::Identities::PublicKey Ark::Crypto::Identities::PublicKey::fromPrivateKey(PrivateKey privateKey)
```

Derive the public from the given private key.

#### Parameters

| Type       | Name             | Required | Description |
| ---------- | ---------------- | -------- | ----------- |
| PrivateKey | privateKey       | Yes      | Private key |

#### Return Value

`Ark::Crypto::Identities::PublicKey`

---

### `fromHex()`

```cpp
Ark::Crypto::Identities::PublicKey Ark::Crypto::Identities::PublicKey::fromHex(const char *const publicKey)
```

Create a public key instance from a hex string.

#### Parameters

| Type     | Name             | Required | Description |
| -------- | ---------------- | -------- | ----------- |
| char     | publicKey        | Yes      | Public key  |

#### Return Value

`Ark::Crypto::Identities::PublicKey`

---

### `validate()`

```cpp
bool Ark::Crypto::Identities::PublicKey::validate(PublicKey publicKey)
```

Validate the given public key.

#### Parameters

| Type      | Name             | Required | Description |
| --------- | ---------------- | -------- | ----------- |
| PublicKey | publicKey        | Yes      | Public key  |

#### Return Value

`bool`

---

### `validate()`

```cpp
bool Ark::Crypto::Identities::PublicKey::validate(const char *publicKeyStr)
```

Validate the given public key.

#### Parameters

| Type      | Name             | Required | Description       |
| --------- | ---------------- | -------- | ----------------- |
| char      | *publicKeyStr    | Yes      | Public key string |

#### Return Value

`bool`

---

### `validate()`

```cpp
bool Ark::Crypto::Identities::PublicKey::validate(const uint8_t *publicKeyBytes)
```

Validate the given public key.

#### Parameters

| Type      | Name             | Required | Description       |
| --------- | ---------------- | -------- | ----------------- |
| uint8_t   | *publicKeyBytes  | Yes      | Public key bytes  |

#### Return Value

`bool`

## Ark::Crypto::Identities::WIF

### `WIF()`

```cpp
Ark::Crypto::Identities::WIF::WIF(const char *const newWIFStr)
```

Constructor of the WIF class.

#### Parameters

| Type | Name             | Required | Description        |
| ---- | ---------------- | -------- | ------------------ |
| char | newWIFStr        | Yes      | Network WIF string |

---

### `WIF()`

```cpp
Ark::Crypto::Identities::WIF::WIF(const uint8_t *newWIFBytes)
```

Constructor of the WIF class.

#### Parameters

| Type    | Name             | Required | Description       |
| ------- | ---------------- | -------- | ----------------- |
| uint8_t | *newWIFBytes     | Yes      | Network WIF bytes |

---

### `toBytes()`

```cpp
const uint8_t *Ark::Crypto::Identities::WIF::toBytes()
```

Convert the private key to its bytes representation.

#### Return Value

`uint8_t`

---

### `toString()`

```cpp
std::string Ark::Crypto::Identities::WIF::toString()
```

Convert the private key to its string representation.

#### Return Value

`std::string`

---

### `fromPassphrase()`

```cpp
Ark::Crypto::Identities::WIF Ark::Crypto::Identities::WIF::fromPassphrase(const char *const passphrase,
                                                                          uint8_t wifByte)
```

Derive the WIF from the given passphrase.

#### Parameters

| Type    | Name             | Required | Description |
| ------- | ---------------- | -------- | ----------- |
| char    | passphrase       | Yes      | Passphrase  |
| uint8_t | wifByte          | Yes      | Network WIF |

#### Return Value

`Ark::Crypto::Identities::WIF`

## Ark::Crypto::Networks::AbstractNetwork

### `getBase58Prefix()`

```cpp
uint8_t Ark::Crypto::Networks::AbstractNetwork::getBase58Prefix(Base58PrefixType prefix)
```

Get the networks Base58 prefix byte given a prefix name.

#### Parameters

| Type             | Name   | Required | Description  |
| ---------------- | ------ | -------- | ------------ |
| Base58PrefixType | prefix | Yes      | Prefix name  |

#### Return Value

`uint8_t`

---

### `setBase58Prefix()`

```cpp
void Ark::Crypto::Networks::AbstractNetwork::setBase58Prefix(Base58PrefixType prefix, uint8_t newByte)
```

Sets the networks Base58 prefix given a prefix name and byte.

#### Parameters

| Type             | Name    | Required | Description  |
| ---------------- | ------- | -------- | ------------ |
| Base58PrefixType | prefix  | Yes      | Prefix name  |
| uint8_t          | newByte | Yes      | Prefix byte  |

#### Return Value

`void`

---

### `getBIP32Prefix()`

```cpp
long Ark::Crypto::Networks::AbstractNetwork::getBIP32Prefix(BIP32PrefixType prefix)
```

Get the networks BIP32 prefix byte given a prefix name.

#### Parameters

| Type             | Name    | Required | Description |
| ---------------- | ------- | -------- | ----------- |
| BIP32PrefixType  | prefix  | Yes      | Prefix name |

#### Return Value

`long`

---

### `setBIP32Prefix()`

```cpp
void Ark::Crypto::Networks::AbstractNetwork::setBIP32Prefix(BIP32PrefixType prefix, long newByte)
```

Sets the networks BIP32 prefix given a prefix name and byte.

#### Parameters

| Type             | Name    | Required | Description |
| ---------------- | ------- | -------- | ----------- |
| BIP32PrefixType  | prefix  | Yes      | Prefix name |
| long             | newByte | Yes      | Prefix byte |

#### Return Value

`void`

---

### `isLocked()`

```cpp
bool Ark::Crypto::Networks::AbstractNetwork::isLocked()
```

Get the network lock.

#### Return Value

`bool`

---

### `epoch()`

```cpp
const char* Ark::Crypto::Networks::AbstractNetwork::epoch()
```

Get the network epoch.

#### Return Value

`char*`

---

### `version()`

```cpp
uint8_t Ark::Crypto::Networks::AbstractNetwork::version()
```

Get the network version.

#### Return Value

`uint8_t`::AbstractNetwork

## Ark::Crypto::Transactions::Builder

### `buildTransfer()`

```cpp
Transaction Builder::buildTransfer(std::string recipientId, uint64_t amount, std::string vendorField,
                                   std::string passphrase, std::string secondPassphrase)
```

Builds a transaction for a transfer.

#### Parameters

| Type        | Name             | Required | Description             |
| ----------- | ---------------- | -------- | ----------------------- |
| std::string | recipientId      | Yes      | Recipient identifier    |
| uint64_t    | amount           | Yes      | Transaction amount      |
| std::string | vendorField      | Yes      | Transaction vendorfield |
| std::string | passphrase       | Yes      | Passphrase              |
| std::string | secondPassphrase | Yes      | Second passphrase       |

#### Return Value

`Transaction`

---

### `buildSecondSignatureRegistration()`

```cpp
Transaction Builder::buildSecondSignatureRegistration(std::string passphrase, std::string secondPassphrase)
```

Builds a transaction for a second signature registration.

#### Parameters

| Type        | Name             | Required | Description       |
| ----------- | ---------------- | -------- | ----------------- |
| std::string | passphrase       | Yes      | Passphrase        |
| std::string | secondPassphrase | Yes      | Second passphrase |

#### Return Value

`Transaction`

---

### `buildDelegateRegistration()`

```cpp
Transaction Builder::buildDelegateRegistration(std::string username, std::string passphrase,
                                               std::string secondPassphrase)
```

Builds a transaction for a delegate registration.

#### Parameters

| Type        | Name             | Required | Description       |
| ----------- | ---------------- | -------- | ----------------- |
| std::string | username         | Yes      | Delegate username |
| std::string | passphrase       | Yes      | Passphrase        |
| std::string | secondPassphrase | Yes      | Second passphrase |

#### Return Value

`Transaction`

---

### `buildVote()`

```cpp
Transaction Builder::buildVote(std::vector<std::string> votes, std::string passphrase, std::string secondPassphrase)
```

Builds a transaction for a vote registration.

#### Parameters

| Type                     | Name             | Required | Description       |
| ------------------------ | ---------------- | -------- | ----------------- |
| std::vector<std::string> | votes            | Yes      | Votes             |
| std::string              | passphrase       | Yes      | Passphrase        |
| std::string              | secondPassphrase | Yes      | Second passphrase |

#### Return Value

`Transaction`

---

### `buildMultiSignatureRegistration()`

```cpp
Transaction Builder::buildMultiSignatureRegistration(uint8_t min, uint8_t lifetime, std::vector<std::string> keysgroup,
                                                     std::string passphrase, std::string secondPassphrase)
```

Builds a transaction for a multi signature registration.

#### Parameters

| Type                     | Name             | Required | Description                              |
| ------------------------ | ---------------- | -------- | ---------------------------------------- |
| uint8_t                  | min              | Yes      | Transaction minimum required signatures  |
| uint8_t                  | lifetime         | Yes      | Transaction lifetime                     |
| std::vector<std::string> | keysgroup        | Yes      | Transaction keysgroup                    |
| std::string              | passphrase       | Yes      | Passphrase                               |
| std::string              | secondPassphrase | Yes      | Second passphrase                        |

#### Return Value

`Transaction`

---

### `sign()`

```cpp
Transaction Builder::sign(Transaction transaction, std::string passphrase, std::string secondPassphrase)
```

Sign the transaction using the given passphrase.

#### Parameters

| Type         | Name             | Required | Description       |
| ------------ | ---------------- | -------- | ----------------- |
| Transaction  | transaction      | Yes      | Transaction       |
| std::string  | passphrase       | Yes      | Passphrase        |
| std::string  | secondPassphrase | No       | Second passphrase |

#### Return Value

`Transaction`

## Ark::Crypto::Transactions::Deserializer

### `deserialize()`

```cpp
Transaction Deserializer::deserialize()
```

Handle the deserialization of transaction data.

#### Return Value

`Transaction`

---

### `deserializeHeader()`

```cpp
void Deserializer::deserializeHeader(Transaction& transaction)
```

Handle the deserialization of "headers" data.

#### Parameters

| Type         | Name             | Required | Description |
| ------------ | ---------------- | -------- | ----------- |
| Transaction& | transaction      | Yes      | Transaction |

#### Return Value

`void`

---

### `deserializeType()`

```cpp
void Deserializer::deserializeType(Transaction& transaction)
```

Handle the deserialization of "type" data.

#### Parameters

| Type         | Name             | Required | Description |
| ------------ | ---------------- | -------- | ----------- |
| Transaction& | transaction      | Yes      | Transaction |

#### Return Value

`void`

---

### `deserializeTransfer()`

```cpp
void Deserializer::deserializeTransfer(Transaction& transaction)
```

Handle the deserialization of "transfer" data.

#### Parameters

| Type         | Name             | Required | Description |
| ------------ | ---------------- | -------- | ----------- |
| Transaction& | transaction      | Yes      | Transaction |

#### Return Value

`void`

---

### `deserializeSecondSignatureRegistration()`

```cpp
void Deserializer::deserializeSecondSignatureRegistration(Transaction& transaction)
```

Handle the deserialization of "second signature" data.

#### Parameters

| Type         | Name             | Required | Description |
| ------------ | ---------------- | -------- | ----------- |
| Transaction& | transaction      | Yes      | Transaction |

#### Return Value

`void`

---

### `deserializeDelegateRegistration()`

```cpp
void Deserializer::deserializeDelegateRegistration(Transaction& transaction)
```

Handle the deserialization of "delegate registration" data.

#### Parameters

| Type         | Name             | Required | Description |
| ------------ | ---------------- | -------- | ----------- |
| Transaction& | transaction      | Yes      | Transaction |

#### Return Value

`void`

---

### `deserializeVote()`

```cpp
void Deserializer::deserializeVote(Transaction& transaction)
```

Handle the deserialization of "vote" data.

#### Parameters

| Type         | Name             | Required | Description |
| ------------ | ---------------- | -------- | ----------- |
| Transaction& | transaction      | Yes      | Transaction |

#### Return Value

`void`

---

### `deserializeMultiSignatureRegistration()`

```cpp
void Deserializer::deserializeMultiSignatureRegistration(Transaction& transaction)
```

Handle the deserialization of "multi signature registration" data.

#### Parameters

| Type         | Name             | Required | Description |
| ------------ | ---------------- | -------- | ----------- |
| Transaction& | transaction      | Yes      | Transaction |

#### Return Value

`void`

---

### `parseSignatureLength()`

```cpp
static uint8_t parseSignatureLength(const std::string& hex)
```

Parse the signature, second signature, and multi signatures length.

#### Parameters

| Type         | Name  | Required | Description |
| ------------ | ----- | -------- | ----------- |
| std::string& | hex   | Yes      | Hex string  |

#### Return Value

`uint8_t`

---

### `deserializeSignatures()`

```cpp
void Deserializer::deserializeSignatures(Transaction& transaction)
```

Handle the deserialization of "signature" data.

#### Parameters

| Type         | Name             | Required | Description |
| ------------ | ---------------- | -------- | ----------- |
| Transaction& | transaction      | Yes      | Transaction |

#### Return Value

`void`

---

### `handleVersionOne()`

```cpp
void Deserializer::handleVersionOne(Transaction& transaction)
```

Handle the deserialization of transaction data with a version of 1.0.

#### Parameters

| Type         | Name             | Required | Description |
| ------------ | ---------------- | -------- | ----------- |
| Transaction& | transaction      | Yes      | Transaction |

#### Return Value

`void`

## Ark::Crypto::Transactions::Serializer

### `serialize()`

```cpp
std::string Serializer::serialize()
```

Handle the serialization of transaction data.

#### Return Value

`std::string`

---

### `serializeVendorField()`

```cpp
void Serializer::serializeVendorField(std::vector<uint8_t>& bytes)
```

Handle the serialization of vendorfield.

#### Parameters

| Type                  | Name   | Required | Description |
| --------------------- | ------ | -------- | ----------- |
| std::vector<uint8_t>& | bytes  | Yes      | Transaction |

#### Return Value

`void`

---

### `serializeType()`

```cpp
void Serializer::serializeType(std::vector<uint8_t>& bytes)
```

Handle the deserialization of "type" data.

#### Parameters

| Type                  | Name   | Required | Description |
| --------------------- | ------ | -------- | ----------- |
| std::vector<uint8_t>& | bytes  | Yes      | Transaction |

#### Return Value

`void`

---

### `serializeTransfer()`

```cpp
void Serializer::serializeTransfer(std::vector<uint8_t>& bytes)
```

Handle the serialization of "transfer" data.

#### Parameters

| Type                  | Name   | Required | Description |
| --------------------- | ------ | -------- | ----------- |
| std::vector<uint8_t>& | bytes  | Yes      | Transaction |

#### Return Value

`void`

---

### `serializeSecondSignatureRegistration()`

```cpp
void Serializer::serializeSecondSignatureRegistration(std::vector<uint8_t>& bytes)
```

Handle the serialization of "second signature registration" data.

#### Parameters

| Type                  | Name   | Required | Description |
| --------------------- | ------ | -------- | ----------- |
| std::vector<uint8_t>& | bytes  | Yes      | Transaction |

#### Return Value

`void`

---

### `serializeDelegateRegistration()`

```cpp
void Serializer::serializeDelegateRegistration(std::vector<uint8_t>& bytes)
```

Handle the serialization of "delegate registration" data.

#### Parameters

| Type                  | Name   | Required | Description |
| --------------------- | ------ | -------- | ----------- |
| std::vector<uint8_t>& | bytes  | Yes      | Transaction |

#### Return Value

`void`

---

### `serializeVote()`

```cpp
void Serializer::serializeVote(std::vector<uint8_t>& bytes)
```

Handle the serialization of "vote" data.

#### Parameters

| Type                  | Name   | Required | Description |
| --------------------- | ------ | -------- | ----------- |
| std::vector<uint8_t>& | bytes  | Yes      | Transaction |

#### Return Value

`void`

---

### `serializeMultiSignatureRegistration()`

```cpp
void Serializer::serializeMultiSignatureRegistration(std::vector<uint8_t>& bytes)
```

Handle the serialization of "multi signature registration" data.

#### Parameters

| Type                  | Name   | Required | Description |
| --------------------- | ------ | -------- | ----------- |
| std::vector<uint8_t>& | bytes  | Yes      | Transaction |

#### Return Value

`void`

---

### `serializeSignatures()`

```cpp
void Serializer::serializeSignatures(std::vector<uint8_t>& bytes)
```

Handle the deserialization of "signature" data.

#### Parameters

| Type                  | Name   | Required | Description |
| --------------------- | ------ | -------- | ----------- |
| std::vector<uint8_t>& | bytes  | Yes      | Transaction |

#### Return Value

`void`

## Ark::Crypto::Transactions::Transaction

### `getId()`

```cpp
std::string Ark::Crypto::Transactions::Transaction::getId()
```

Convert the byte representation to a unique identifier.

#### Return Value

`std::string`

---

### `sign()`

```cpp
std::string Ark::Crypto::Transactions::Transaction::sign(const char* passphrase)
```

Sign the transaction using the given passphrase.

#### Parameters

| Type  | Name       | Required | Description |
| ----- | ---------- | -------- | ----------- |
| char* | passphrase | Yes      | Passphrase  |

#### Return Value

`std::string`

---

### `secondSign()`

```cpp
std::string Ark::Crypto::Transactions::Transaction::secondSign(const char* passphrase)
```

Sign the transaction using the given second passphrase.

#### Parameters

| Type  | Name       | Required | Description        |
| ----- | ---------- | -------- | ------------------ |
| char* | passphrase | Yes      | Second passphrase  |

#### Return Value

`std::string`

---

### `verify()`

```cpp
bool Ark::Crypto::Transactions::Transaction::verify()
```

Verify the transaction.

#### Return Value

`bool`

---

### `secondVerify()`

```cpp
bool Ark::Crypto::Transactions::Transaction::secondVerify(const char* secondPublicKey)
```

Verify the transaction with a second public key.

#### Parameters

| Type   | Name            | Required | Description       |
| ------ | --------------- | -------- | ----------------- |
| char*  | secondPublicKey | Yes      | Second public key |

#### Return Value

`bool`

---

### `internalVerify()`

```cpp
bool Ark::Crypto::Transactions::Transaction::internalVerify(
    std::string publicKey,
    std::vector<uint8_t> bytes,
    std::string signature)
```

Verify the transaction with a second public key.

#### Parameters

| Type                 | Name      | Required | Description       |
| -------------------- | --------- | -------- | ----------------- |
| std::string          | publicKey | Yes      | Public key        |
| std::vector<uint8_t> | bytes     | Yes      | ...               |
| std::string          | signature | Yes      | Signature         |

#### Return Value

`bool`

---

### `toArray()`

```cpp
std::map<std::string, std::string> Ark::Crypto::Transactions::Transaction::toArray()
```

Convert the transaction to its array representation.

#### Return Value

`std::map<std::string, std::string>`

---

### `toJson()`

```cpp
std::string Ark::Crypto::Transactions::Transaction::toJson()
```

Convert the transaction to its JSON representation.

#### Return Value

`std::string`

---

### `toBytes()`

```cpp
std::vector<uint8_t> Ark::Crypto::Transactions::Transaction::toBytes(
    bool skipSignature,
    bool skipSecondSignature)
```

Convert the transaction to its byte representation.

#### Parameters

| Type  | Name                  | Required | Description           |
| ----- | --------------------- | -------- | --------------------- |
| bool  | skipSignature         | No       | Skip first signature  |
| bool  | skipSecondSignature   | No       | Skip second signature |

#### Return Value

`std::vector<uint8_t>`

---

## Ark::Crypto::Utils::Message::Message

### `Message()`

```cpp
Ark::Crypto::Utils::Message::Message(
    std::string msg,
    PublicKey pubKey,
    std::vector<uint8_t> sig)
    : message(msg),
      publicKey(pubKey),
      signature(sig)
```

Create a new message instance

#### Parameters

| Type                 | Name       | Required | Description |
| -------------------- | ---------- | -------- | ----------- |
| std::string          | msg        | Yes      | Message     |
| PublicKey            | pubKey     | Yes      | Public key  |
| std::vector<uint8_t> | signature  | Yes      | Signature   |

---

### `sign()`

```cpp
bool Ark::Crypto::Utils::Message::sign(
    std::string newMessage,
    const char *const passphrase)
```

Sign a message using the given passphrase.

#### Parameters

| Type        | Name       | Required | Description |
| ----------- | ---------- | -------- | ----------- |
| std::string | newMessage | Yes      | Message     |
| char        | passphrase | Yes      | Passphrase  |

#### Return Value

`bool`

---

### `verify()`

```cpp
bool Ark::Crypto::Utils::Message::verify()
```

Verify the message contents

#### Return Value

`bool`

---

### `toArray()`

```cpp
std::map<std::string, std::string> Ark::Crypto::Utils::Message::toArray()
```

Convert the message to its array representation

#### Return Value

`std::map<std::string, std::string>`

---

### `toJson()`

```cpp
std::string Ark::Crypto::Utils::Message::toJson()
```

Convert the message to its JSON representation

#### Return Value

`std::string`

## Ark::Crypto::Utils::Slot

### `time()`

```cpp
uint64_t Ark::Crypto::Utils::Slot::time(Crypto::Networks::AbstractNetwork network)
```

Get the time diff between now and network start.

#### Parameters

| Type            | Name       | Required | Description |
| --------------- | ---------- | -------- | ----------- |
| AbstractNetwork | network    | Yes      | Network     |

#### Return Value

`uint64_t`

---

### `now()`

```cpp
uint64_t Ark::Crypto::Utils::Slot::now()
```

Get the time now.

#### Return Value

`uint64_t`

---

### `epoch()`

```cpp
uint64_t Ark::Crypto::Utils::Slot::epoch(Crypto::Networks::AbstractNetwork network)
```

Get the network start epoch.

#### Parameters

| Type            | Name       | Required | Description |
| --------------- | ---------- | -------- | ----------- |
| AbstractNetwork | network    | Yes      | Network     |

#### Return Value

`uint64_t`

---

### `epoch()`

```cpp
#if defined(ESP32) || defined(ESP8266)
uint64_t Ark::Crypto::Utils::Slot::epoch(Crypto::Networks::AbstractNetwork network)
```

Get the network start epoch.

#### Parameters

| Type            | Name       | Required | Description |
| --------------- | ---------- | -------- | ----------- |
| AbstractNetwork | network    | Yes      | Network     |

#### Return Value

`uint64_t`

---

### `epoch()`

```cpp
#if defined(ESP32) || defined(ESP8266)
uint64_t Ark::Crypto::Utils::Slot::now()
```

Get the network epoch.

#### Return Value

`uint64_t`