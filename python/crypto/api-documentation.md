---
id: api-documentation
title: API Documentation
---

# API Documentation

## crypto.configuration.fee

### `get_fee()`

```python
def get_fee(transaction_type):
```

Get a fee for a given transaction type

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| int | transaction\_type | Yes | Transaction type for which we wish to get a fee |

#### Return Value

`<class 'int'>`

### `set_fee()`

```python
def set_fee(transaction_type, value):
```

Set a fee

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| int | transaction\_type | Yes | Transaction type for which we wish to set a fee |
| int | value | Yes | Fee for a given transaction type |

#### Return Value

`<class 'NoneType'>`

## crypto.configuration.network

### `set_network()`

```python
def set_network(network_object):
```

Set what network you want to use in the crypto library

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| Network | network\_object | Yes | Testnet, Devnet, Mainnet |

#### Return Value

`<class 'NoneType'>`

### `get_network()`

```python
def get_network():
```

Get settings for a selected network, default network is devnet

#### Return Value

`<class 'dict'>`

### `set_custom_network()`

```python
def set_custom_network(epoch, version, wif):
```

Set custom network

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| datetime | epoch | Yes | Network epoch time |
| int | version | Yes | Network version |
| int | wif | Yes | Network WIF |

#### Return Value

`<class 'NoneType'>`

## crypto.identity.address

### `address_from_public_key()`

```python
def address_from_public_key(public_key, network_version=None):
```

Get an address from a public key

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| str | public\_key | Yes | Public key |
| int | network\_version | No | Version of the network |

#### Return Value

`<class 'str'>`

### `address_from_private_key()`

```python
def address_from_private_key(private_key, network_version=None):
```

Get an address from private key

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| str | private\_key | Yes | Private key |
| int | network\_version | No | Version of the network |

#### Return Value

`<class 'str'>`

### `address_from_passphrase()`

```python
def address_from_passphrase(passphrase, network_version=None):
```

Get an address from passphrase

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| str | passphrase | Yes | Passphrase |
| int | network\_version | No | Version of the network |

#### Return Value

`<class 'str'>`

### `validate_address()`

```python
def validate_address(address, network_version=None):
```

Validate a given address

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| str | address | Yes | Address to validate |
| int | network\_version | No | Version of the network |

#### Return Value

`<class 'bool'>`

## crypto.identity.private\_key.PrivateKey

### `sign()`

```python
def sign(self, message):
```

Sign a message with this private key object

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| str | message | Yes | Bytes data you want to sign |

#### Return Value

`<class 'NoneType'>`

### `to_hex()`

```python
def to_hex(self):
```

Returns a private key in hex format

#### Return Value

`<class 'str'>`

### `from_passphrase()`

```python
def from_passphrase(cls, passphrase):
```

Create PrivateKey object from a given passphrase

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| str | passphrase | Yes | Passphrase |

#### Return Value

`<class 'PrivateKey'>`

### `from_hex()`

```python
def from_hex(self, private_key):
```

Create PrivateKey object from a given hex private key

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| str | private\_key | Yes | Private key |

#### Return Value

`<class 'PrivateKey'>`

## crypto.identity.public\_key.PublicKey

### `to_hex()`

```python
def to_hex(self):
```

Returns a public key in hex format

#### Return Value

`<class 'str'>`

### `from_passphrase()`

```python
def from_passphrase(cls, passphrase):
```

Create PublicKey object from a given passphrase

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| str | passphrase | Yes | Passphrase |

#### Return Value

`<class 'PublicKey'>`

### `from_hex()`

```python
def from_hex(cls, public_key):
```

Create PublicKey object from a given hex private key

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| str | public\_key | Yes | Public key |

#### Return Value

`<class 'PublicKey'>`

## crypto.identity.wif

### `wif_from_passphrase()`

```python
def wif_from_passphrase(passphrase, network_wif=None):
```

Get wif from passphrase

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| str | passphrase | Yes | Passphrase |
| int | network\_wif | No | Network WIF |

#### Return Value

`<class 'str'>`

## crypto.transactions.builder.base.BaseTransactionBuilder

### `to_dict()`

```python
def to_dict(self):
```

Convert the transaction to its dictionary representation.

#### Return Value

`<class 'dict'>`

### `to_json()`

```python
def to_json(self):
```

Convert the transaction to its JSON representation

#### Return Value

`<class 'dict'>`

### `sign()`

```python
def sign(self, passphrase):
```

Sign the transaction using the given passphrase

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| str | passphrase | Yes | Passphrase associated with the account sending this transaction |

#### Return Value

`<class 'NoneType'>`

### `second_sign()`

```python
def second_sign(self, passphrase):
```

Sign the transaction using the given second passphrase

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| str | passphrase | Yes | Second passphrase associated with the account sending this transaction |

#### Return Value

`<class 'NoneType'>`

### `verify()`

```python
def verify(self):
```

Verify the transaction validity

#### Return Value

`<class 'bool'>`

### `second_verify()`

```python
def second_verify(self):
```

Verify the transaction validity with a second signature

#### Return Value

`<class 'bool'>`

## crypto.transactions.builder.delegate\_registration.DelegateRegistration

### `__init__()`

```python
def __init__(self, username, fee=None):
```

Create a new DelegateRegistration transaction instance

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| str | username | Yes | Delegate username |
| int | fee | No | Transaction fee |

#### Return Value

`<class 'crypto.transactions.builder.delegate_registration.DelegateRegistration'>`

### `sign()`

```python
def sign(self, passphrase):
```

Sign the transaction using the given passphrase

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| str | passphrase | Yes | Passphrase |

#### Return Value

`<class 'NoneType'>`

## crypto.transactions.builder.delegate\_resignation.DelegateResignation

### `__init__()`

```python
def __init__(self, fee=None):
```

Create a new DelegateResignation transaction instance

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| int | fee | No | Transaction fee |

#### Return Value

`<class 'crypto.transactions.builder.delegate_resignation.DelegateResignation'>`

## crypto.transactions.builder.ipfs.IPFS

### `__init__()`

```python
def __init__(self, fee=None):
```

Create a new IPFS transaction instance

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| int | fee | No | Transaction fee |

#### Return Value

`<class 'crypto.transactions.builder.ipfs.IPFS'>`

## crypto.transactions.builder.multi\_payment.MultiPayment

### `__init__()`

```python
def __init__(self, fee=None):
```

Create a new MultiPayment transaction instance

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| int | fee | No | Transaction fee |

#### Return Value

`<class 'crypto.transactions.builder.multi_payment.MultiPayment'>`

## crypto.transactions.builder.multi\_signature\_registration.MultiSignatureRegistration

### `__init__()`

```python
def __init__(self, min_signatures, lifetime, keysgroup, fee=None):
```

Create a new MultiSignatureRegistration transaction instance

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| int | min\_signatures | Yes | Transaction minimum required signatures |
| int | lifetime | Yes | Transaction lifetime |
| list | keysgroup | Yes | Transaction keygroups |
| int | fee | No | Transaction fee |

#### Return Value

`<class 'crypto.transactions.builder.multi_signature_registration.MultiSignatureRegistration'>`

## crypto.transactions.builder.second\_signature\_registration.SecondSignatureRegistration

### `__init__()`

```python
def __init__(self, second_passphrase, fee=None):
```

Create a new SecondSignatureRegistration transaction instance

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| str | second\_passphrase | No | Second passphrase |
| int | fee | No | Transaction fee |

#### Return Value

`<class 'crypto.transactions.builder.second_signature_registration.SecondSignatureRegistration'>`

## crypto.transactions.builder.timelock\_transfer.TimelockTransfer

### `__init__()`

```python
def __init__(self, fee=None):
```

Create a new TimelockTransfer transaction instance

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| int | fee | No | Transaction fee |

#### Return Value

`<class 'crypto.transactions.builder.timelock_transfer.TimelockTransfer'>`

## crypto.transactions.builder.Transfer.Transfer

### `__init__()`

```python
def __init__(self, recipientId, amount, vendorField=None, fee=None):
```

Create a new Transfer transaction instance

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| str | recipientId | Yes | Recipient identifier |
| int | amount | Yes | Transaction amount |
| str | vendorField | No | Transaction vendorfield |
| int | fee | No | Transaction fee |

#### Return Value

`<class 'crypto.transactions.builder.transfer.Transfer'>`

## crypto.transactions.builder.vote.Vote

### `__init__()`

```python
def __init__(self, vote, fee=None):
```

Create a new Vote transaction instance

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| str | vote | Yes | Vote |
| int | fee | No | Transaction fee |

#### Return Value

`<class 'crypto.transactions.builder.vote.Vote'>`

### `sign()`

```python
def sign(self, passphrase):
```

Sign the transaction using the given passphrase

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| str | passphrase | Yes | Passphrase |

#### Return Value

`<class 'NoneType'>`

## crypto.transactions.deserializers.base

### `__init__()`

```python
def __init__(self, serialized, asset_offset, transaction):
```

Create a new deserializer instance

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| ??? | serialized | Yes | Serialized |
| ??? | asset\_offset | Yes | Offset |
| ??? | transaction | Yes | Transaction |

#### Return Value

`<class 'crypto.transactions.deserializers.base.BaseDeserializer'>`

### `deserialize()`

```python
def deserialize(self):
```

Handle the deserialization of transaction data

#### Return Value

`NotImplementedError`

## crypto.transactions.deserializers.delegate\_registration

### `deserialize()`

```python
def deserialize(self):
```

Handle the deserialization of "delegate registration" data

#### Return Value

`<class 'dict'>`

## crypto.transactions.deserializers.multi\_signature\_registration

### `deserialize()`

```python
def deserialize(self):
```

Handle the deserialization of "multi signature registration" data

#### Return Value

`<class 'dict'>`

## crypto.transactions.deserializers.second\_signature\_registration

### `deserialize()`

```python
def deserialize(self):
```

Handle the deserialization of "second signature" data.

#### Return Value

`<class 'dict'>`

## crypto.transactions.deserializers.transfer

### `deserialize()`

```python
def deserialize(self):
```

Handle the deserialization of "transfer" data

#### Return Value

`<class 'dict'>`

## crypto.transactions.deserializers.vote

### `deserialize()`

```python
def deserialize(self):
```

Handle the deserialization of "vote" data.

#### Return Value

`<class 'dict'>`

## crypto.transactions.serializers.base

### `__init__()`

```python
def __init__(self, transaction, byte_data=bytes()):
```

Create a new serializer instance

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| Transaction | transaction | Yes | Transaction |
| bytes | byte\_data | No | ... |

#### Return Value

`<class 'crypto.transactions.serializers.base.BaseSerializer'>`

### `serialize`

```python
def serialize(self):
```

Handle the serialization of transaction data

#### Return Value

`NotImplementedError`

## crypto.transactions.serializers.delegate\_registration

### `serialize`

```python
def serialize(self):
```

Handle the serialization of "delegate registration" data

#### Return Value

`<class 'bytes'>`

## crypto.transactions.serializers.delegate\_resignation

### `serialize`

```python
def serialize(self):
```

Handle the serialization of "delegate resignation" data

#### Return Value

`<class 'bytes'>`

## crypto.transactions.serializers.ipfs

### `serialize`

```python
def serialize(self):
```

Handle the serialization of "ipfs" data

#### Return Value

`<class 'bytes'>`

## crypto.transactions.serializers.multi\_payment

### `serialize`

```python
def serialize(self):
```

Handle the serialization of "multi payment" data

#### Return Value

`<class 'bytes'>`

## crypto.transactions.serializers.multi\_signature\_registration

### `serialize`

```python
def serialize(self):
```

Handle the serialization of "multi signature" data

#### Return Value

`<class 'bytes'>`

## crypto.transactions.serializers.second\_signature\_registration

### `serialize`

```python
def serialize(self):
```

Handle the serialization of "second signature" data

#### Return Value

`<class 'bytes'>`

## crypto.transactions.serializers.timelock\_transfer

### `serialize`

```python
def serialize(self):
```

Handle the serialization of "timelock" data

#### Return Value

`<class 'bytes'>`

## crypto.transactions.serializers.transfer

### `serialize`

```python
def serialize(self):
```

Handle the serialization of "transfer" data

#### Return Value

`<class 'bytes'>`

## crypto.transactions.serializers.vote

### `serialize`

```python
def serialize(self):
```

Handle the serialization of "vote" data

#### Return Value

`<class 'bytes'>`

## crypto.transactions.deserializer

### `__init__`

```python
def __init__(self, serialized):
```

Create a new deserializer instance

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| str | serialized | Yes | Serialized |

#### Return Value

`<class 'crypto.transactions.deserializer.Deserializer'>`

### `deserialize`

```python
def deserialize(self):
```

Perform AIP11 compliant deserialization

#### Return Value

`<class 'crypto.transactions.transaction.Transaction'>`

### `_handle_transaction_type`

```python
def _handle_transaction_type(self, asset_offset, transaction):
```

Handle the deserialization of transaction data

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| int | asset\_offset | Yes | Offset |
| transaction.Transaction | transaction | Yes | Transaction |

#### Return Value

`<class 'crypto.transactions.transaction.Transaction'>`

### `_handle_version_one`

```python
def _handle_version_one(self, transaction):
```

Handle the deserialization of transaction data with a version of 1.0

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| transaction.Transaction | transaction | Yes | Transaction |

#### Return Value

`<class 'crypto.transactions.transaction.Transaction'>`

### `_handle_version_two`

```python
def _handle_version_two(self, transaction):
```

Handle the deserialization of transaction data with a version of 2.0.

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| transaction.Transaction | transaction | Yes | Transaction |

#### Return Value

`<class 'NoneType'>`

## crypto.transactions.serializer

### `__init__`

```python
def __init__(self, transaction):
```

Create a new serializer instance

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| transaction.Transaction | transaction | Yes | Transaction |

#### Return Value

`<class 'crypto.transactions.serializer.Serializer'>`

### `serialize`

```python
def serialize(self):
```

Perform AIP11 compliant serialization

#### Return Value

`<class 'str'>`

### `_handle_transaction_type`

```python
def _handle_transaction_type(self, bytes_data):
```

Handle the serialization of transaction data

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| bytes | bytes\_data | Yes | ... |

#### Return Value

`<class 'bytes'>`

### `_handle_signature`

```python
def _handle_signature(self, bytes_data):
```

Handle the serialization of "signatures" data

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| bytes | bytes\_data | Yes | ... |

#### Return Value

`<class 'bytes'>`

## crypto.transactions.transaction

### `__init__`

```python
def __init__(self, *args, **kwargs):
```

Create a new transaction instance

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| any | \*args | No | ... |
| any | \*\*kwargs | No | ... |

#### Return Value

`<class 'crypto.transactions.transaction.Transaction'>`

### `get_id`

```python
def get_id(self):
```

Convert the byte representation to a unique identifier

#### Return Value

`<class 'str'>`

### `to_dict`

```python
def to_dict(self):
```

Convert the transaction to its dictionary representation.

#### Return Value

`<class 'dict'>`

### `to_json`

```python
def to_json(self):
```

Convert the transaction to its JSON representation

#### Return Value

`<class 'dict'>`

### `to_bytes`

```python
def to_bytes(self, skip_signature=True, skip_second_signature=True):
```

Convert the transaction to its byte representation

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| bool | skip\_signature | Yes | Skip first signature |
| bool | skip\_second\_signature | Yes | Skip second signature |

#### Return Value

`<class 'bytes'>`

### `parse_signatures`

```python
def parse_signatures(self, serialized, start_offset):
```

Parse the signature, second signature and multi signatures

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| str | serialized | Yes | Serialized |
| int | start\_offset | Yes | Offset |

#### Return Value

`<class 'NoneType'>`

### `serialize`

```python
def serialize(self):
```

Perform AIP11 compliant serialization

#### Return Value

`<class 'str'>`

### `deserialize`

```python
def deserialize(self, serialized):
```

Perform AIP11 compliant deserialization

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| str | serialized | Yes | Serialized |

#### Return Value

`<class 'str'>`

### `verify`

```python
def verify(self):
```

Verify the transaction

#### Return Value

`<class 'NoneType'>`

### `second_verify`

```python
def second_verify(self, passphrase):
```

Verify the transaction using the 2nd passphrase

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| str | passphrase | Yes | Second passphrase |

#### Return Value

`<class 'NoneType'>`

### `_handle_transaction_type`

```python
def _handle_transaction_type(self, bytes_data):
```

Handle each transaction type differently

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| bytes | bytes\_data | Yes | Input the bytes data to which you want to append new bytes |

#### Return Value

`<class 'bytes'>`

### `_handle_signature`

```python
def _handle_signature(self, bytes_data, skip_signature, skip_second_signature):
```

Handle the serialization of "signatures" data

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| bytes | bytes\_data | Yes | Input the bytes data to which you want to append new bytes from signature |
| bool | skip\_signature | Yes | Skip first signature |
| bool | skip\_second\_signature | Yes | Skip second signature |

#### Return Value

`<class 'bytes'>`

## crypto.utils.message

### `__init__`

```python
def __init__(self, message, signature, public_key):
```

Create a new message instance

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| str | message | Yes | Message |
| str | signature | Yes | Signature |
| str | public\_key | Yes | Public key |

#### Return Value

`<class 'crypto.utils.message.Message'>`

### `sign`

```python
def sign(cls, message, passphrase):
```

Sign a message using the given passphrase

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| str | message | Yes | Message |
| str | passphrase | Yes | Passphrase |

#### Return Value

`<class 'crypto.utils.message.Message'>`

### `verify`

```python
def verify(self):
```

Verify the message contents

#### Return Value

`<class 'bool'>`

### `to_dict`

```python
def to_dict(self):
```

Convert the message to its dictionary representation

#### Return Value

`<class 'dict'>`

### `to_json`

```python
def to_json(self):
```

Convert the message to its JSON representation

#### Return Value

`<class 'dict'>`

## crypto.utils.slot

### `get_time`

```python
def get_time():
```

Get the time diff between now and network start

#### Return Value

`<class 'int'>`

### `get_epoch`

```python
def get_epoch():
```

Get the network start epoch

#### Return Value

`<class 'datetime'>`

