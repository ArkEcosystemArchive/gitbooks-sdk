---
id: api-documentation
title: API Documentation
---

## crypto.configuration.fee

### `get_fee()`


```py
def get_fee(transaction_type):
```

Get a fee for a given transaction type

#### Parameters

| Type | Name             | Required | Description                                     |
| ---- | ---------------- | -------- | ----------------------------------------------- |
| int  | transaction_type | Yes      | Transaction type for which we wish to get a fee |


#### Return Value

`<class 'int'>`

---

### `set_fee()`

```py
def set_fee(transaction_type, value):
```

Set a fee

#### Parameters

| Type | Name             | Required | Description                                     |
| ---- | ---------------- | -------- | ----------------------------------------------- |
| int  | transaction_type | Yes      | Transaction type for which we wish to set a fee |
| int  | value            | Yes      | Fee for a given transaction type                |

#### Return Value

`<class 'NoneType'>`

## crypto.configuration.network

### `set_network()`

```py
def set_network(network_object):
```

Set what network you want to use in the crypto library

#### Parameters

| Type     | Name             | Required | Description              |
| -------- | ---------------- | -------- | ------------------------ |
| Network  | network_object   | Yes      | Testnet, Devnet, Mainnet |

#### Return Value

`<class 'NoneType'>`

---

### `get_network()`

```py
def get_network():
```

Get settings for a selected network, default network is devnet

#### Return Value

`<class 'dict'>`

---

### `set_custom_network()`

```py
def set_custom_network(epoch, version, wif):
```

Set custom network

#### Parameters

| Type     | Name    | Required | Description        |
| -------- | --------| -------- | ------------------ |
| datetime | epoch   | Yes      | Network epoch time |
| int      | version | Yes      | Network version    |
| int      | wif     | Yes      | Network WIF        | 

#### Return Value

`<class 'NoneType'>`

## crypto.identity.address

### `address_from_public_key()`

```py
def address_from_public_key(public_key, network_version=None):
```

Get an address from a public key

#### Parameters

| Type     | Name             | Required | Description            |
| -------- | ---------------- | -------- | ---------------------- |
| str      | public_key       | Yes      | Public key             |
| int      | network_version  | No       | Version of the network |

#### Return Value

`<class 'str'>`

---

### `address_from_private_key()`

```py
def address_from_private_key(private_key, network_version=None):
```

Get an address from private key

#### Parameters

| Type     | Name             | Required | Description            |
| -------- | ---------------- | -------- | ---------------------- |
| str      | private_key      | Yes      | Private key            |
| int      | network_version  | No       | Version of the network |

#### Return Value

`<class 'str'>`

---

### `address_from_passphrase()`

```py
def address_from_passphrase(passphrase, network_version=None):
```

Get an address from passphrase

#### Parameters

| Type     | Name             | Required | Description            |
| -------- | ---------------- | -------- | ---------------------- |
| str      | passphrase       | Yes      | Passphrase             |
| int      | network_version  | No       | Version of the network |

#### Return Value

`<class 'str'>`

---

### `validate_address()`

```py
def validate_address(address, network_version=None):
```

Validate a given address

#### Parameters

| Type     | Name             | Required | Description            |
| -------- | ---------------- | -------- | ---------------------- |
| str      | address          | Yes      | Address to validate    |
| int      | network_version  | No       | Version of the network |

#### Return Value

`<class 'bool'>`

## crypto.identity.private_key.PrivateKey

### `sign()`

```py
def sign(self, message):
```

Sign a message with this private key object

#### Parameters

| Type     | Name             | Required | Description                         |
| -------- | ---------------- | -------- | ----------------------------------- |
| str      | message          | Yes      | Bytes data you want to sign         |

#### Return Value

`<class 'NoneType'>`

---

### `to_hex()`

```py
def to_hex(self):
```

Returns a private key in hex format

#### Return Value

`<class 'str'>`

---

### `from_passphrase()`

```py
def from_passphrase(cls, passphrase):
```

Create PrivateKey object from a given passphrase

#### Parameters

| Type     | Name             | Required | Description |
| -------- | ---------------- | -------- | ----------- |
| str      | passphrase       | Yes      | Passphrase  |

#### Return Value

`<class 'PrivateKey'>`

---

### `from_hex()`

```py
def from_hex(self, private_key):
```

Create PrivateKey object from a given hex private key

#### Parameters

| Type     | Name             | Required | Description |
| -------- | ---------------- | -------- | ----------- |
| str      | private_key      | Yes      | Private key |

#### Return Value

`<class 'PrivateKey'>`

## crypto.identity.public_key.PublicKey

### `to_hex()`

```py
def to_hex(self):
```

Returns a public key in hex format

#### Return Value

`<class 'str'>`

---

### `from_passphrase()`

```py
def from_passphrase(cls, passphrase):
```

Create PublicKey object from a given passphrase

#### Parameters

| Type     | Name             | Required | Description |
| -------- | ---------------- | -------- | ----------- |
| str      | passphrase       | Yes      | Passphrase  |

#### Return Value

`<class 'PublicKey'>`

---

### `from_hex()`

```py
def from_hex(cls, public_key):
```

Create PublicKey object from a given hex private key

#### Parameters

| Type     | Name             | Required | Description |
| -------- | ---------------- | -------- | ----------- |
| str      | public_key       | Yes      | Public key  |

#### Return Value

`<class 'PublicKey'>`

## crypto.identity.wif

### `wif_from_passphrase()`

```py
def wif_from_passphrase(passphrase, network_wif=None):
```

Get wif from passphrase

#### Parameters

| Type     | Name             | Required | Description |
| -------- | ---------------- | -------- | ----------- |
| str      | passphrase       | Yes      | Passphrase  |
| int      | network_wif      | No       | Network WIF |

#### Return Value

`<class 'str'>`

## crypto.transactions.builder.base.BaseTransactionBuilder

### `to_dict()`

```py
def to_dict(self):
```

Convert the transaction to its dictionary representation.

#### Return Value

`<class 'dict'>`

---

### `to_json()`

```py
def to_json(self):
```

Convert the transaction to its JSON representation

#### Return Value

`<class 'dict'>`

---

### `sign()`

```py
def sign(self, passphrase):
```

Sign the transaction using the given passphrase

#### Parameters

| Type     | Name             | Required | Description                                                     |
| -------- | ---------------- | -------- | --------------------------------------------------------------- |
| str      | passphrase       | Yes      | Passphrase associated with the account sending this transaction |

#### Return Value

`<class 'NoneType'>`

---

### `second_sign()`

```py
def second_sign(self, passphrase):
```

Sign the transaction using the given second passphrase

#### Parameters

| Type     | Name             | Required | Description                                                            |
| -------- | ---------------- | -------- | ---------------------------------------------------------------------- |
| str      | passphrase       | Yes      | Second passphrase associated with the account sending this transaction |

#### Return Value

`<class 'NoneType'>`

---

### `verify()`

```py
def verify(self):
```

Verify the transaction validity

#### Return Value

`<class 'bool'>`

---

### `second_verify()`

```py
def second_verify(self):
```

Verify the transaction validity with a second signature

#### Return Value

`<class 'bool'>`

## crypto.transactions.builder.delegate_registration.DelegateRegistration

### `__init__()`

```py
def __init__(self, username, fee=None):
```

Create a new DelegateRegistration transaction instance

#### Parameters

| Type     | Name             | Required | Description       |
| -------- | ---------------- | -------- | ----------------- |
| str      | username         | Yes      | Delegate username |
| int      | fee              | No       | Transaction fee   |

#### Return Value

`<class 'crypto.transactions.builder.delegate_registration.DelegateRegistration'>`

---

### `sign()`

```py
def sign(self, passphrase):
```

Sign the transaction using the given passphrase

#### Parameters

| Type     | Name             | Required | Description |
| -------- | ---------------- | -------- | ----------- |
| str      | passphrase       | Yes      | Passphrase  |

#### Return Value

`<class 'NoneType'>`

## crypto.transactions.builder.delegate_resignation.DelegateResignation

### `__init__()`

```py
def __init__(self, fee=None):
```

Create a new DelegateResignation transaction instance

#### Parameters

| Type     | Name  | Required | Description     |
| -------- | ----- | -------- | --------------- |
| int      | fee   | No       | Transaction fee |

#### Return Value

`<class 'crypto.transactions.builder.delegate_resignation.DelegateResignation'>`

## crypto.transactions.builder.ipfs.IPFS

### `__init__()`

```py
def __init__(self, fee=None):
```

Create a new IPFS transaction instance

#### Parameters

| Type     | Name  | Required | Description     |
| -------- | ----- | -------- | --------------- |
| int      | fee   | No       | Transaction fee |

#### Return Value

`<class 'crypto.transactions.builder.ipfs.IPFS'>`

## crypto.transactions.builder.multi_payment.MultiPayment

### `__init__()`

```py
def __init__(self, fee=None):
```

Create a new MultiPayment transaction instance

#### Parameters

| Type     | Name  | Required | Description     |
| -------- | ----- | -------- | --------------- |
| int      | fee   | No       | Transaction fee |

#### Return Value

`<class 'crypto.transactions.builder.multi_payment.MultiPayment'>`

## crypto.transactions.builder.multi_signature_registration.MultiSignatureRegistration

### `__init__()`

```py
def __init__(self, min_signatures, lifetime, keysgroup, fee=None):
```

Create a new MultiSignatureRegistration transaction instance

#### Parameters

| Type     | Name             | Required | Description                             |
| -------- | ---------------- | -------- | --------------------------------------- |
| int      | min_signatures   | Yes      | Transaction minimum required signatures |
| int      | lifetime         | Yes      | Transaction lifetime                    |
| list     | keysgroup        | Yes      | Transaction keygroups                   |
| int      | fee              | No       | Transaction fee                         |

#### Return Value

`<class 'crypto.transactions.builder.multi_signature_registration.MultiSignatureRegistration'>`

## crypto.transactions.builder.second_signature_registration.SecondSignatureRegistration

### `__init__()`

```py
def __init__(self, second_passphrase, fee=None):
```

Create a new SecondSignatureRegistration transaction instance

#### Parameters

| Type     | Name              | Required | Description       |
| -------- | ----------------- | -------- | ----------------- |
| str      | second_passphrase | No       | Second passphrase |
| int      | fee               | No       | Transaction fee   |

#### Return Value

`<class 'crypto.transactions.builder.second_signature_registration.SecondSignatureRegistration'>`

## crypto.transactions.builder.timelock_transfer.TimelockTransfer

### `__init__()`

```py
def __init__(self, fee=None):
```

Create a new TimelockTransfer transaction instance

#### Parameters

| Type     | Name  | Required | Description     |
| -------- | ----- | -------- | --------------- |
| int      | fee   | No       | Transaction fee |

#### Return Value

`<class 'crypto.transactions.builder.timelock_transfer.TimelockTransfer'>`

## crypto.transactions.builder.Transfer.Transfer

### `__init__()`

```py
def __init__(self, recipientId, amount, vendorField=None, fee=None):
```

Create a new Transfer transaction instance

#### Parameters

| Type     | Name             | Required | Description             |
| -------- | ---------------- | -------- | ----------------------- |
| str      | recipientId      | Yes      | Recipient identifier    |
| int      | amount           | Yes      | Transaction amount      |
| str      | vendorField      | No       | Transaction vendorfield |
| int      | fee              | No       | Transaction fee         |

#### Return Value

`<class 'crypto.transactions.builder.transfer.Transfer'>`

## crypto.transactions.builder.vote.Vote

### `__init__()`

```py
def __init__(self, vote, fee=None):
```

Create a new Vote transaction instance

#### Parameters

| Type     | Name             | Required | Description     |
| -------- | ---------------- | -------- | --------------- |
| str      | vote             | Yes      | Vote            |
| int      | fee              | No       | Transaction fee |

#### Return Value

`<class 'crypto.transactions.builder.vote.Vote'>`

### `sign()`

```py
def sign(self, passphrase):
```

Sign the transaction using the given passphrase

#### Parameters

| Type     | Name             | Required | Description |
| -------- | ---------------- | -------- | ----------- |
| str      | passphrase       | Yes      | Passphrase  |

#### Return Value

`<class 'NoneType'>`

## crypto.transactions.deserializers.base

### `__init__()`

```py
def __init__(self, serialized, asset_offset, transaction):
```

Create a new deserializer instance

#### Parameters

| Type     | Name             | Required | Description |
| -------- | ---------------- | -------- | ----------- |
| ???      | serialized       | Yes      | Serialized  |
| ???      | asset_offset     | Yes      | Offset      |
| ???      | transaction      | Yes      | Transaction |

#### Return Value

`<class 'crypto.transactions.deserializers.base.BaseDeserializer'>`

---

### `deserialize()`

```py
def deserialize(self):
```

Handle the deserialization of transaction data

#### Return Value

`NotImplementedError`

## crypto.transactions.deserializers.delegate_registration

### `deserialize()`

```py
def deserialize(self):
```

Handle the deserialization of "delegate registration" data

#### Return Value

`<class 'dict'>`

## crypto.transactions.deserializers.multi_signature_registration

### `deserialize()`

```py
def deserialize(self):
```

Handle the deserialization of "multi signature registration" data

#### Return Value

`<class 'dict'>`

## crypto.transactions.deserializers.second_signature_registration

### `deserialize()`

```py
def deserialize(self):
```

Handle the deserialization of "second signature" data.

#### Return Value

`<class 'dict'>`

## crypto.transactions.deserializers.transfer

### `deserialize()`

```py
def deserialize(self):
```

Handle the deserialization of "transfer" data

#### Return Value

`<class 'dict'>`

## crypto.transactions.deserializers.vote

### `deserialize()`

```py
def deserialize(self):
```

Handle the deserialization of "vote" data.

#### Return Value

`<class 'dict'>`

## crypto.transactions.serializers.base

### `__init__()`

```py
def __init__(self, transaction, byte_data=bytes()):
```

Create a new serializer instance

#### Parameters

| Type        | Name             | Required | Description |
| ----------- | ---------------- | -------- | ----------- |
| Transaction | transaction      | Yes      | Transaction |
| bytes       | byte_data        | No       | ...         |

#### Return Value

`<class 'crypto.transactions.serializers.base.BaseSerializer'>`

---

### `serialize`

```py
def serialize(self):
```

Handle the serialization of transaction data

#### Return Value

`NotImplementedError`

## crypto.transactions.serializers.delegate_registration

### `serialize`

```py
def serialize(self):
```

Handle the serialization of "delegate registration" data

#### Return Value

`<class 'bytes'>`

## crypto.transactions.serializers.delegate_resignation

### `serialize`

```py
def serialize(self):
```

Handle the serialization of "delegate resignation" data

#### Return Value

`<class 'bytes'>`

## crypto.transactions.serializers.ipfs

### `serialize`

```py
def serialize(self):
```

Handle the serialization of "ipfs" data

#### Return Value

`<class 'bytes'>`

## crypto.transactions.serializers.multi_payment

### `serialize`

```py
def serialize(self):
```

Handle the serialization of "multi payment" data

#### Return Value

`<class 'bytes'>`

## crypto.transactions.serializers.multi_signature_registration

### `serialize`

```py
def serialize(self):
```

Handle the serialization of "multi signature" data

#### Return Value

`<class 'bytes'>`

## crypto.transactions.serializers.second_signature_registration

### `serialize`

```py
def serialize(self):
```

Handle the serialization of "second signature" data

#### Return Value

`<class 'bytes'>`

## crypto.transactions.serializers.timelock_transfer

### `serialize`

```py
def serialize(self):
```

Handle the serialization of "timelock" data

#### Return Value

`<class 'bytes'>`

## crypto.transactions.serializers.transfer

### `serialize`

```py
def serialize(self):
```

Handle the serialization of "transfer" data

#### Return Value

`<class 'bytes'>`

## crypto.transactions.serializers.vote

### `serialize`

```py
def serialize(self):
```

Handle the serialization of "vote" data

#### Return Value

`<class 'bytes'>`

## crypto.transactions.deserializer

### `__init__`

```py
def __init__(self, serialized):
```

Create a new deserializer instance

#### Parameters

| Type     | Name             | Required | Description |
| -------- | ---------------- | -------- | ----------- |
| str      | serialized       | Yes      | Serialized  |

#### Return Value

`<class 'crypto.transactions.deserializer.Deserializer'>`

---

### `deserialize`

```py
def deserialize(self):
```

Perform AIP11 compliant deserialization

#### Return Value

`<class 'crypto.transactions.transaction.Transaction'>`

---

### `_handle_transaction_type`

```py
def _handle_transaction_type(self, asset_offset, transaction):
```

Handle the deserialization of transaction data

#### Parameters

| Type                    | Name             | Required | Description |
| ------------------------| ---------------- | -------- | ----------- |
| int                     | asset_offset     | Yes      | Offset      |
| transaction.Transaction | transaction      | Yes      | Transaction |

#### Return Value

`<class 'crypto.transactions.transaction.Transaction'>`

---

### `_handle_version_one`

```py
def _handle_version_one(self, transaction):
```

Handle the deserialization of transaction data with a version of 1.0

#### Parameters

| Type                    | Name             | Required | Description |
| ------------------------| ---------------- | -------- | ----------- |
| transaction.Transaction | transaction      | Yes      | Transaction |

#### Return Value

`<class 'crypto.transactions.transaction.Transaction'>`

---

### `_handle_version_two`

```py
def _handle_version_two(self, transaction):
```

Handle the deserialization of transaction data with a version of 2.0.

#### Parameters

| Type                    | Name             | Required | Description |
| ------------------------| ---------------- | -------- | ----------- |
| transaction.Transaction | transaction      | Yes      | Transaction |

#### Return Value

`<class 'NoneType'>`

## crypto.transactions.serializer

### `__init__`

```py
def __init__(self, transaction):
```

Create a new serializer instance

#### Parameters

| Type                    | Name             | Required | Description |
| ------------------------| ---------------- | -------- | ----------- |
| transaction.Transaction | transaction      | Yes      | Transaction |

#### Return Value

`<class 'crypto.transactions.serializer.Serializer'>`

---

### `serialize`

```py
def serialize(self):
```

Perform AIP11 compliant serialization

#### Return Value

`<class 'str'>`

---

### `_handle_transaction_type`

```py
def _handle_transaction_type(self, bytes_data):
```

Handle the serialization of transaction data

#### Parameters

| Type  | Name       | Required | Description |
| ----- | ---------- | -------- | ----------- |
| bytes | bytes_data | Yes      | ...         |

#### Return Value

`<class 'bytes'>`

---

### `_handle_signature`

```py
def _handle_signature(self, bytes_data):
```

Handle the serialization of "signatures" data

#### Parameters

| Type  | Name       | Required | Description |
| ----- | ---------- | -------- | ----------- |
| bytes | bytes_data | Yes      | ...         |

#### Return Value

`<class 'bytes'>`

## crypto.transactions.transaction

### `__init__`

```py
def __init__(self, *args, **kwargs):
```

Create a new transaction instance

#### Parameters

| Type  | Name       | Required | Description |
| ----- | ---------- | -------- | ----------- |
| any   | *args      | No       | ...         |
| any   | **kwargs   | No       | ...         |

#### Return Value

`<class 'crypto.transactions.transaction.Transaction'>`

---

### `get_id`

```py
def get_id(self):
```

Convert the byte representation to a unique identifier

#### Return Value

`<class 'str'>`

---

### `to_dict`

```py
def to_dict(self):
```

Convert the transaction to its dictionary representation.

#### Return Value

`<class 'dict'>`

---

### `to_json`

```py
def to_json(self):
```

Convert the transaction to its JSON representation

#### Return Value

`<class 'dict'>`

---

### `to_bytes`

```py
def to_bytes(self, skip_signature=True, skip_second_signature=True):
```

Convert the transaction to its byte representation

#### Parameters

| Type  | Name                  | Required | Description           |
| ----- | --------------------- | -------- | --------------------- |
| bool  | skip_signature        | Yes      | Skip first signature  |
| bool  | skip_second_signature | Yes      | Skip second signature |

#### Return Value

`<class 'bytes'>`

---

### `parse_signatures`

```py
def parse_signatures(self, serialized, start_offset):
```

Parse the signature, second signature and multi signatures

#### Parameters

| Type  | Name         | Required | Description |
| ----- | ------------ | -------- | ----------- |
| str   | serialized   | Yes      | Serialized  |
| int   | start_offset | Yes      | Offset      |

#### Return Value

`<class 'NoneType'>`

---

### `serialize`

```py
def serialize(self):
```

Perform AIP11 compliant serialization

#### Return Value

`<class 'str'>`

---

### `deserialize`

```py
def deserialize(self, serialized):
```

Perform AIP11 compliant deserialization

#### Parameters

| Type  | Name       | Required | Description |
| ----- | ---------- | -------- | ----------- |
| str   | serialized | Yes      | Serialized  |

#### Return Value

`<class 'str'>`

---

### `verify`

```py
def verify(self):
```

Verify the transaction

#### Return Value

`<class 'NoneType'>`

---

### `second_verify`

```py
def second_verify(self, passphrase):
```

Verify the transaction using the 2nd passphrase

#### Parameters

| Type  | Name       | Required | Description       |
| ----- | ---------- | -------- | ----------------- |
| str   | passphrase | Yes      | Second passphrase |

#### Return Value

`<class 'NoneType'>`

---

### `_handle_transaction_type`

```py
def _handle_transaction_type(self, bytes_data):
```

Handle each transaction type differently

#### Parameters

| Type  | Name       | Required | Description                                                |
| ----- | ---------- | -------- | ---------------------------------------------------------- |
| bytes | bytes_data | Yes      | Input the bytes data to which you want to append new bytes |

#### Return Value

`<class 'bytes'>`

---

### `_handle_signature`

```py
def _handle_signature(self, bytes_data, skip_signature, skip_second_signature):
```

Handle the serialization of "signatures" data

#### Parameters

| Type  | Name                  | Required | Description                                                               |
| ----- | --------------------- | -------- | ------------------------------------------------------------------------- |
| bytes | bytes_data            | Yes      | Input the bytes data to which you want to append new bytes from signature |
| bool  | skip_signature        | Yes      | Skip first signature                                                      |
| bool  | skip_second_signature | Yes      | Skip second signature                                                     |

#### Return Value

`<class 'bytes'>`

## crypto.utils.message

### `__init__`

```py
def __init__(self, message, signature, public_key):
```

Create a new message instance

#### Parameters

| Type  | Name       | Required | Description |
| ----- | ---------- | -------- | ----------- |
| str   | message    | Yes      | Message     |
| str   | signature  | Yes      | Signature   |
| str   | public_key | Yes      | Public key  |

#### Return Value

`<class 'crypto.utils.message.Message'>`

---

### `sign`

```py
def sign(cls, message, passphrase):
```

Sign a message using the given passphrase

#### Parameters

| Type  | Name       | Required | Description |
| ----- | ---------- | -------- | ----------- |
| str   | message    | Yes      | Message     |
| str   | passphrase | Yes      | Passphrase  |

#### Return Value

`<class 'crypto.utils.message.Message'>`

---

### `verify`

```py
def verify(self):
```

Verify the message contents

#### Return Value

`<class 'bool'>`

---

### `to_dict`

```py
def to_dict(self):
```

Convert the message to its dictionary representation

#### Return Value

`<class 'dict'>`

---

### `to_json`

```py
def to_json(self):
```

Convert the message to its JSON representation

#### Return Value

`<class 'dict'>`

## crypto.utils.slot

### `get_time`

```py
def get_time():
```

Get the time diff between now and network start

#### Return Value

`<class 'int'>`

---

### `get_epoch`

```py
def get_epoch():
```

Get the network start epoch

#### Return Value

`<class 'datetime'>`