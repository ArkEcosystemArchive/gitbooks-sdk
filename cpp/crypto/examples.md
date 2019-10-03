---
id: examples
title: Examples
---

## Initialization

```cpp
#include <arkCrypto.h>
```

## Transactions

A transaction is an object specifying the transfer of funds from the sender's wallet to the recipient's. Each transaction must be signed by the sender's private key to prove authenticity and origin. After broadcasting through the [client SDK](/cpp/client/api-documentation#initialization), a transaction is permanently incorporated in the blockchain by a Delegate Node.

### Sign

The crypto SDK can sign a transaction using your private key or passphrase (from which the private key is generated). Ensure you are familiar with [digital signatures](https://en.wikipedia.org/wiki/Digital_signature) before using the crypto SDKs.

```cpp
Ark::Crypto::Transactions::Transaction transfer = Ark::Crypto::Transactions::Builder::buildTransfer(
    "recipientID",
    1000000000,
    "vendorfield",
    "passphrase",
    "secondPassphrase");

/* We can also do this manually */

Ark::Crypto::Transactions::Transaction transaction;
transaction.type = Ark::Crypto::Enums::Types::TRANSFER;
transaction.fee = Ark::Crypto::Configuration::Fee().get(Ark::Crypto::Enums::Types::TRANSFER);
transaction.recipientId = "recipientId";
transaction.amount = 1000000000;
transaction.vendorField = "vendorfield";

std::string signature = sign(transaction, "passphrase", "secondPassphrase");

>>> std::string
```

### Serialize (AIP11)

> Serialization of a transaction object ensures it is compact and properly formatted to be incorporated in the ARK blockchain. If you are using the crypto SDK in combination with the public API SDK, you should not need to serialize manually.

```cpp
Ark::Crypto::Transactions::Transaction transfer = Ark::Crypto::Transactions::Builder::buildTransfer(
    "recipientID",
    1000000000,
    "vendorfield",
    "passphrase",
    "secondPassphrase");

Ark::Crypto::Transactions::Serializer serializer(transfer);
std::string serializedTransaction = serializer.serialize();

>>> std::string
```

### Deserialize (AIP11)

> A serialized transaction may be deserialized for inspection purposes. The public API does not return serialized transactions, so you should only need to deserialize in exceptional circumstances.

```cpp
Ark::Crypto::Transactions::Deserializer deserializer("serialized_transaction");
auto actual = deserializer.deserialize();

>>> Transaction
```

## Message

The crypto SDK not only supports transactions but can also work with other arbitrary data (expressed as strings).

### Sign

> Signing a string works much like signing a transaction: in most implementations, the message is hashed, and the resulting hash is signed using the `private key` or `passphrase`.

```cpp
const auto text = "Computer science is no more about computers than astronomy is about telescopes.";
const auto passphrase = "bullet parade snow bacon mutual deposit brass floor staff list concert ask";
Ark::Crypto::Utils::Message message;
message.sign(text, passphrase);

>>> bool
```

### Verify

> A message's signature can easily be verified by hash, without the private key that signed the message, by using the `verify` method.

```cpp
const auto text = "Computer science is no more about computers than astronomy is about telescopes.";
Ark::Crypto::Identities::PublicKey publicKey = Ark::Crypto::Identities::PublicKey::fromHex("validHexString");
std::vector<uint8_t> signature = HexToBytes("validHexString");

Ark::Crypto::Utils::Message message(
    text,
    publicKey,
    signature
);

bool isValid = message.verify();

>>> bool
```

## Identities

> The identities class allows for the creation and inspection of keypairs from `passphrases`. Here you find vital functions when creating transactions and managing wallets.

### Derive the Address from a Passphrase

```cpp
const auto passphrase = "bullet parade snow bacon mutual deposit brass floor staff list concert ask";
const uint8_t networkVersion = 0x1E;
Ark::Crypto::Identities::Address address = Ark::Crypto::Identities::Address::fromPassphrase(passphrase, networkVersion);

>>> Ark::Crypto::Identities::Address
```

### Derive the Address from a Public Key

```cpp
Ark::Crypto::Identities::PublicKey publicKey("029fdf41a7d69d8efc7b236c21b9509a23d862ea4ed8b13a56e31eee58dbfd97b4");
const uint8_t networkVersion = 0x1E;
Ark::Crypto::Identities::Address address = Ark::Crypto::Identities::Address::fromPublicKey(publicKey, networkVersion);

>>> Ark::Crypto::Identities::Address
```

### Derive the Address from a Private Key

```cpp
PrivateKey privateKey("validPrivateKey");
const uint8_t networkVersion = 0x1E;
Ark::Crypto::Identities::Address address = Ark::Crypto::Identities::Address::fromPrivateKey(privateKey, networkVersion);

>>> Ark::Crypto::Identities::Address
```

### Validate an Address

```cpp
Ark::Crypto::Identities::Address address("validAddress");
const uint8_t networkVersion = 0x1E;
bool isValid = Ark::Crypto::Identities::Address::validate(address, networkVersion);

>>> bool
```

## Private Key

> As the name implies, private keys and passphrases are to remain private. Never store these unencrypted and minimize access to these secrets

### Derive the Private Key from a Passphrase

```cpp
const auto passphrase = "bullet parade snow bacon mutual deposit brass floor staff list concert ask";
Ark::Crypto::Identities::PrivateKey privateKey = Ark::Crypto::Identities::PrivateKey::fromPassphrase(passphrase);

>>> Ark::Crypto::Identities::PrivateKey
```

### Derive the Private Key Instance Object from a Hexadecimal Encoded String

```cpp
Ark::Crypto::Identities::PrivateKey privateKey = Ark::Crypto::Identities::PrivateKey::fromHex("validHexString");

>>> Ark::Crypto::Identities::PrivateKey
```

### Derive the Private Key from a WIF

```cpp
const char* wifStr = "validWIF";
Ark::Crypto::Identities::PrivateKey privateKey = Ark::Crypto::Identities::PrivateKey::fromWIFString(wifStr, wifByte);

>>> Ark::Crypto::Identities::PrivateKey
```

## Public Key

> Public Keys may be freely shared, and are included in transaction objects to validate the authenticity.

### Derive the Public Key from a Passphrase

```cpp
const auto passphrase = "bullet parade snow bacon mutual deposit brass floor staff list concert ask";
Ark::Crypto::Identities::PublicKey publicKey = Ark::Crypto::Identities::PublicKey::fromPassphrase(passphrase);

>>> Ark::Crypto::Identities::PublicKey
```

### Derive the Public Key Instance Object from a Hexadecimal Encoded String

```cpp
Ark::Crypto::Identities::PublicKey publicKey = Ark::Crypto::Identities::PublicKey::fromHex("validHexString");


>>> Ark::Crypto::Identities::PublicKey
```

### Validate a Public Key

```cpp
Ark::Crypto::Identities::PublicKey publicKey("validPublicKey");
bool isValid = Ark::Crypto::Identities::PublicKey::validate(publicKey);

>>> Ark::Crypto::Identities::PublicKey
```

## WIF

> The WIF should remain secret, just like your `passphrase` and `private key`.

### Derive the WIF from a Passphrase

```cpp
const auto passphrase = "bullet parade snow bacon mutual deposit brass floor staff list concert ask";
const uint8_t wifByte = 0xaa;
Ark::Crypto::Identities::WIF wif = Ark::Crypto::Identities::WIF::fromPassphrase(passphrase, wifByte);

>>> Ark::Crypto::Identities::WIF
```
