---
id: api-documentation
title: API Documentation
---

# API Documentation

## Crypto\Managers\configManager

### `setConfig()`

```typescript
public setConfig(config: INetworkConfig)
```

Set the configuration.

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| INetworkConfig | config | Yes | Network configuration object |

#### Return Value

`void`

### `setFromPreset()`

```typescript
public setFromPreset(network: NetworkName)
```

Set the configuration from given presets.

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| NetworkName | network | Yes | Preset |

#### Return Value

`void`

### `getPreset()`

```typescript
public getPreset(network: NetworkName)
```

Get configuration preset.

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| NetworkName | network | Yes | Preset |

#### Return Value

`INetworkConfig`

### `all()`

```typescript
public all()
```

Get all configs.

#### Return Value

`INetworkConfig`

### `set()`

```typescript
public set<T = any>(key: string, value: T)
```

Set a value for the specified network config key.

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| string | key | Yes | Key to set |
| T | value | Yes | Value to set |

#### Return Value

`void`

### `get()`

```typescript
public get<T = any>(key: string)
```

Get key.

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| string | key | Yes | Key to get |

#### Return Value

`T`

### `setHeight()`

```typescript
public setHeight(value: number)
```

Set network height.

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| number | value | Yes | Network height |

#### Return Value

`void`

### `getHeight()`

```typescript
public getHeight()
```

Get network height.

#### Return Value

`number`

### `isNewMilestone()`

```typescript
public isNewMilestone(): boolean
```

Verify if current height contains a milestone.

#### Return Value

`boolean`

### `getMilestone()`

```typescript
public getMilestone(height?: number)
```

Get milestone.

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| number | height | No | Network height |

#### Return Value

`{ [key: string]: any }`

### `getMilestones()`

```typescript
public getMilestones()
```

Get all milestones.

#### Return Value

`any`

## Crypto\Managers\feeManager

### `set()`

```typescript
public set(type: TransactionTypes | number, value: number)
```

Set a fee.

#### Parameters

| Type | Name | Required | Description |  |
| :--- | :--- | :--- | :--- | :--- |
| TransactionTypes | number | type | Yes | Transaction type |
| number | value | Yes | Fee value |  |

#### Return Value

`void`

### `get()`

```typescript
public get(type: TransactionTypes | number)
```

Get a fee for a given transaction type.

#### Parameters

| Type | Name | Required | Description |  |
| :--- | :--- | :--- | :--- | :--- |
| TransactionTypes | number | type | Yes | Transaction type |

#### Return Value

`BigNumber`

### `getForTransaction()`

```typescript
public getForTransaction(transaction: ITransactionData)
```

Get a fee for a given transaction.

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| ITransactionData | transaction | Yes | Transaction |

#### Return Value

`BigNumber`

## Crypto\Managers\NetworkManager

### `all()`

```typescript
public static all()
```

Get settings for all networks.

#### Return Value

`Record<NetworkName, INetworkConfig>`

### `findByName()`

```typescript
public static findByName(name: NetworkName)
```

Get settings for a selected network, default network is devnet.

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| NetworkName | name | Yes | Network name |

#### Return Value

`INetworkConfig`

## Crypto\Identities\Address

### `fromPublicKey()`

```typescript
public static fromPublicKey(publicKey: string, networkVersion?: number)
```

Derive the address from the given public key.

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| string | publicKey | Yes | Public key |
| number | networkVersion | No | Version of the network |

#### Return Value

`string`

```typescript
public static fromMultiSignatureAsset(asset: IMultiSignatureAsset, networkVersion?: number)
```

Derive a (multisig) address from a multi signature asset

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| string | asset | Yes | Multi signature asset |
| number | networkVersion | No | Version of the network |

#### Return Value

`string`


### `fromPrivateKey()`

```typescript
public static fromPrivateKey(privateKey, networkVersion?: number)
```

Derive the address from the given private key.

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| string | privateKey | Yes | Private key |
| number | networkVersion | No | Version of the network |

#### Return Value

`string`

### `fromPassphrase()`

```typescript
public static fromPassphrase(passphrase: string, networkVersion?: number)
```

Derive the address from the given passphrase.

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| string | passphrase | Yes | Passphrase |
| number | networkVersion | No | Version of the network |

#### Return Value

`string`

### `fromMultiSignatureAsset()`

```typescript
public static fromMultiSignatureAsset(asset: IMultiSignatureAsset, networkVersion?: number)
```

Derive the address from the given multi signature asset.

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| IMultiSignatureAsset | asset | Yes | Address to validate |
| number | networkVersion | No | Version of the network |

#### Return Value

`string`

### `validate()`

```typescript
public static validate(address: string, networkVersion?: number)
```

Validate the given address.

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| string | address | Yes | Address to validate |
| number | networkVersion | No | Version of the network |

#### Return Value

`boolean`

## Crypto\Identities\Keys

### `fromPassphrase()`

```typescript
public static fromPassphrase(passphrase: string, compressed: boolean = true)
```

Derive the keys from the given passphrase.

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| string | passphrase | Yes | Passphrase |
| boolean | compressed | No | Compression flag |

#### Return Value

`IKeyPair`

### `fromPrivateKey()`

```typescript
public static fromPrivateKey(privateKey: Buffer | string, compressed: boolean = true)
```

Derive the keys from the given private key.

#### Parameters

| Type | Name | Required | Description |  |
| :--- | :--- | :--- | :--- | :--- |
| Buffer | string | privateKey | Yes | Private key |
| boolean | compressed | No | Compression flag |  |

#### Return Value

`IKeyPair`

### `fromWIF()`

```typescript
public static fromWIF(wifKey: string, network?: INetwork)
```

Derive the keys from the given WIF.

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| string | wifKey | Yes | Private key |
| INetwork | network | No | Network |

#### Return Value

`IKeyPair`

## Crypto\Identities\PrivateKey

### `fromPassphrase()`

```typescript
public static fromPassphrase(passphrase: string)
```

Derive the private key for the given passphrase.

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| string | passphrase | Yes | Passphrase |

#### Return Value

`string`

### `fromWIF()`

```typescript
public static fromWIF(wif: string, network?: NetworkType)
```

Create a private key instance from a hex string.

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| string | wif | Yes | Network WIF |
| NetworkType | network | No | Network |

#### Return Value

`string`

## Crypto\Identities\PublicKey

### `fromPassphrase()`

```typescript
public static fromPassphrase(passphrase: string)
```

Derive the public key from the given passphrase.

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| string | passphrase | Yes | Passphrase |

#### Return Value

`string`

### `fromWIF()`

```typescript
public static fromWIF(wif: string, network?: NetworkType)
```

Derive the public key from the given WIF.

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| string | passphrase | Yes | Passphrase |
| NetworkType | network | No | Network |

#### Return Value

`string`

### `fromMultiSignatureAsset()`

```typescript
public static fromMultiSignatureAsset(asset: IMultiSignatureAsset)
```

Derive the public key from the given multi signature asset.

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| IMultiSignatureAsset | asset | Yes | Asset |

#### Return Value

`string`

### `validate()`

```typescript
public static validate(publicKey: string, networkVersion?: number)
```

Validate the given public key.

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| string | publicKey | Yes | Public key |
| number | networkVersion | No | Network version |

#### Return Value

`boolean`

## Crypto\Identities\WIF

### `fromPassphrase()`

```typescript
public static fromPassphrase(passphrase: string, network?: INetwork)
```

Derive the WIF from the given passphrase.

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| str | paspphrase | Yes | Passphrase |
| INetwork | network | No | Network wif |

#### Return Value

`string`

### `fromKeys()`

```typescript
public static fromKeys(keys: IKeyPair, network?: INetwork)
```

Derive the WIF from the given keys.

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| IKeyPair | keys | Yes | Keys |
| INetwork | network | No | Network |

#### Return Value

`string`

## Crypto\Transactions\Builders\Transactions\Transaction

### `build()`

```typescript
public build(data: Partial<ITransactionData> = {})
```

Create a new transaction instance.

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| Partial | data | Yes | Data |

#### Return Value

`ITransaction`

### `version()`

```typescript
public version(version: number)
```

Set the version.

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| number | version | Yes | Network |

#### Return Value

`TBuilder`

### `network()`

```typescript
public network(network: number)
```

Set the network.

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| number | network | Yes | Network |

#### Return Value

`TBuilder`

### `fee()`

```typescript
public fee(fee: string)
```

Set the transaction fee.

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| string | fee | Yes | Transaction fee |

#### Return Value

`TBuilder`

### `amount()`

```typescript
public amount(amount: string)
```

Set the amount of the transaction.

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| string | amount | Yes | Transaction amount |

#### Return Value

`TBuilder`

### `recipientId()`

```typescript
public recipientId(recipientId: string)
```

Set the recipient of the transaction.

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| string | recipientId | Yes | Recipient identifier |

#### Return Value

`TBuilder`

### `senderPublicKey()`

```typescript
public senderPublicKey(publicKey: string)
```

Set the public key of the transaction.

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| string | publicKey | Yes | Public key |

#### Return Value

`TBuilder`

### `vendorField()`

```typescript
public vendorField(vendorField: string)
```

Set the vendorfield of the transaction.

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| string | vendorField | Yes | Vendorfield |

#### Return Value

`TBuilder`

### `sign()`

```typescript
public sign(passphrase: string)
```

Sign the transaction using the given passphrase.

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| string | passphrase | Yes | Passphrase associated with the account sending this transaction |

#### Return Value

`TBuilder`

### `signWithWif()`

```typescript
public signWithWif(wif: string, networkWif?: number)
```

Sign the transaction using the given WIF.

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| string | wif | Yes | Passphrase associated with the account sending this transaction |
| number | networkWif | Yes | Network WIF |

#### Return Value

`TBuilder`

### `secondSign()`

```typescript
public secondSign(secondPassphrase: string)
```

Sign the transaction using the given second passphrase

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| string | secondPassphrase | Yes | Second passphrase associated with the account sending this transaction |

#### Return Value

`TBuilder`

### `secondSignWithWif()`

```typescript
public secondSignWithWif(wif: string, networkWif?: number)
```

Sign the transaction using the given WIF.

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| string | wif | Yes | Network WIF |
| number | networkWif | Yes | Network WIF |

#### Return Value

`TBuilder`

### `multiSign()`

```typescript
public multiSign(passphrase: string, index: number)
```

Multi sign the transaction.

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| string | passphrase | Yes | Passphrase |
| number | index | Yes | ... |

#### Return Value

`TBuilder`

### `verify()`

```typescript
public verify()
```

Verify the transaction validity.

#### Return Value

`boolean`

### `getStruct()`

```typescript
public getStruct()
```

Get transaction structure.

#### Return Value

`ITransactionData`

## Crypto\Transactions\Builders\Transactions\DelegateRegistration

### `usernameAsset()`

```typescript
public usernameAsset(username: string)
```

Set the username to assign.

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| string | username | Yes | Delegate username |

#### Return Value

`DelegateRegistrationBuilder`

### `getStruct()`

```typescript
public getStruct()
```

Get transaction structure.

#### Return Value

`ITransactionData`

## Crypto\Transactions\Builders\Transactions\DelegateResignation

### `getStruct()`

```typescript
public getStruct()
```

Get transaction structure.

#### Return Value

`ITransactionData`

## Crypto\Transactions\Builders\Transactions\IPFS

### `ipfsAsset()`

```typescript
public ipfsAsset(ipfsId: string)
```

Set IPFS asset.

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| string | ipfsId | Yes | IPFS ID |

#### Return Value

`IPFSBuilder`

### `getStruct()`

```typescript
public getStruct()
```

Get transaction structure.

#### Return Value

`ITransactionData`

## Crypto\Transactions\Builders\Transactions\MultiPayment

### `addPayment()`

```typescript
public addPayment(recipientId: string, amount: number)
```

Add a new payment to the collection.

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| string | recipientId | Yes | Recipient identifier |
| number | amount | Yes | Transaction amount |

#### Return Value

`MultiPaymentBuilder`

### `getStruct()`

```typescript
public getStruct()
```

Get transaction structure.

#### Return Value

`ITransactionData`

## Crypto\Transactions\Builders\Transactions\MultiSignature

### `participant()`

```typescript
public participant(publicKey: string)
```

Add participant to multi signature transaction.

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| string | publicKey | Yes | Public key |

#### Return Value

`MultiSignatureBuilder`

### `min()`

```typescript
public min(min: number)
```

Set the minimum required signatures.

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| number | min | Yes | Minimum required signatures |

#### Return Value

`MultiSignatureBuilder`

### `multiSignatureAsset()`

```typescript
public multiSignatureAsset(multiSignature: IMultiSignatureAsset)
```

Derive the address from the given multi signature asset.

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| IMultiSignatureAsset | multiSignature | Yes | Multi signature asset |

#### Return Value

`MultiPaymentBuilder`

### `getStruct()`

```typescript
public getStruct()
```

Get transaction structure.

#### Return Value

`ITransactionData`

## Crypto\Transactions\Builders\Transactions\SecondSignature

### `signature()`

```typescript
public signatureAsset(secondPassphrase: string)
```

Set the signature asset to register the second passphrase.

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| str | secondPassphrase | Yes | Second passphrase |

#### Return Value

`SecondSignatureBuilder`

### `getStruct()`

```typescript
public getStruct()
```

Get transaction structure.

#### Return Value

`ITransactionData`

## Crypto\Transactions\Builders\Transactions\TimelockTransfer

### `timelock`

```typescript
public timelock(timelock: number, timelockType: number)
```

Set the timelock of the transfer.

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| number | timelock | Yes | Timelock time |
| number | timelockType | Yes | Timelock type |

#### Return Value

`TimelockTransferBuilder`

### `getStruct()`

```typescript
public getStruct()
```

Get transaction structure.

#### Return Value

`ITransactionData`

## Crypto\Transactions\Builders\Transactions\Transfer

### `recipient()`

```typescript
public expiration(expiration: number)
```

Set the expiration of the transfer.

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| number | expiration | Yes | Transaction expiration |

#### Return Value

`TransferBuilder`

### `getStruct()`

```typescript
public getStruct()
```

Get transaction structure.

#### Return Value

`ITransactionData`

## Crypto\Transactions\Builders\Transactions\Vote

### `votes()`

```typescript
public votesAsset(votes: string[])
```

Set the votes to cast.

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| string\[\] | votes | Yes | Votes |

#### Return Value

`VoteBuilder`

### `getStruct()`

```typescript
public getStruct()
```

Get transaction structure.

#### Return Value

`ITransactionData`

## Crypto\Transactions\Types\DelegateRegistration

### `getSchema()`

```typescript
public static getSchema()
```

Get transaction schema.

#### Return Value

`schemas.TransactionSchema`

### `serialize()`

```typescript
public serialize(options?: ISerializeOptions)
```

Handle the serialization of "delegate registration" data.

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| ISerializeOptions | options | No | Options |

#### Return Value

`ByteBuffer`

### `deserialize()`

```typescript
public deserialize(buf: ByteBuffer)
```

Handle the deserialization of "delegate registration" data.

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| ByteBuffer | buf | Yes | Buffer |

#### Return Value

`void`

## Crypto\Transactions\Types\DelegateResignation

### `getSchema()`

```typescript
public static getSchema()
```

Get transaction schema.

#### Return Value

`schemas.TransactionSchema`

### `serialize()`

```typescript
public serialize(options?: ISerializeOptions)
```

Handle the serialization of "delegate resignation" data.

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| ISerializeOptions | options | No | Options |

#### Return Value

`ByteBuffer`

### `deserialize()`

```typescript
public deserialize(buf: ByteBuffer)
```

Handle the deserialization of "delegate resignation" data.

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| ByteBuffer | buf | Yes | Buffer |

#### Return Value

`void`

## Crypto\Transactions\Types\Factory

### `initialize()`

```typescript
public static initialize(
        coreTypes: Map<TransactionTypes, TransactionConstructor>,
        customTypes: Map<TransactionTypes, TransactionConstructor>,
    )
```

Transaction factory.

### `create()`

```typescript
public static create(data: ITransactionData)
```

Create a new factory.

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| ITransactionData | data | Yes | Transaction |

#### Return Value

`ITransaction`

### `get()`

```typescript
public static get(type: TransactionTypes | number)
```

Get factory.

#### Parameters

| Type | Name | Required | Description |  |
| :--- | :--- | :--- | :--- | :--- |
| TransactionTypes | number | type | Yes | Transaction |

#### Return Value

`TransactionConstructor`

## Crypto\Transactions\Types\IPFS

### `getSchema()`

```typescript
public static getSchema()
```

Get transaction schema.

#### Return Value

`schemas.TransactionSchema`

### `serialize()`

```typescript
public serialize(options?: ISerializeOptions)
```

Handle the serialization of "IPFS" data.

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| ISerializeOptions | options | No | Options |

#### Return Value

`ByteBuffer`

### `deserialize()`

```typescript
public deserialize(buf: ByteBuffer)
```

Handle the deserialization of "IPFS" data.

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| ByteBuffer | buf | Yes | Buffer |

#### Return Value

`void`

## Crypto\Transactions\Types\MultiPayments

### `getSchema()`

```typescript
public static getSchema()
```

Get transaction schema.

#### Return Value

`schemas.TransactionSchema`

### `serialize()`

```typescript
public serialize(options?: ISerializeOptions)
```

Handle the serialization of "multi payments" data.

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| ISerializeOptions | options | No | Options |

#### Return Value

`ByteBuffer`

### `deserialize()`

```typescript
public deserialize(buf: ByteBuffer)
```

Handle the deserialization of "multi payments" data.

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| ByteBuffer | buf | Yes | Buffer |

#### Return Value

`void`

## Crypto\Transactions\Types\MultiSignature

### `getSchema()`

```typescript
public static getSchema()
```

Get transaction schema.

#### Return Value

`schemas.TransactionSchema`

### `serialize()`

```typescript
public serialize(options?: ISerializeOptions)
```

Handle the serialization of "multi signatures" data.

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| ISerializeOptions | options | No | Options |

#### Return Value

`ByteBuffer`

### `deserialize()`

```typescript
public deserialize(buf: ByteBuffer)
```

Handle the deserialization of "multi signatures" data.

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| ByteBuffer | buf | Yes | Buffer |

#### Return Value

`void`

## Crypto\Transactions\Types\TimelockTransfer

### `getSchema()`

```typescript
public static getSchema()
```

Get transaction schema.

#### Return Value

`schemas.TransactionSchema`

### `serialize()`

```typescript
public serialize(options?: ISerializeOptions)
```

Handle the serialization of "timelock transfer" data.

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| ISerializeOptions | options | No | Options |

#### Return Value

`ByteBuffer`

### `deserialize()`

```typescript
public deserialize(buf: ByteBuffer)
```

Handle the deserialization of "timelock transfer" data.

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| ByteBuffer | buf | Yes | Buffer |

#### Return Value

`void`

## Crypto\Transactions\Types\DelegateRegistration

### `getSchema()`

```typescript
public static getSchema()
```

Get transaction schema.

#### Return Value

`schemas.TransactionSchema`

### `serialize()`

```typescript
public serialize(options?: ISerializeOptions)
```

Handle the serialization of "delegate registration" data.

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| ISerializeOptions | options | No | Options |

#### Return Value

`ByteBuffer`

### `deserialize()`

```typescript
public deserialize(buf: ByteBuffer)
```

Handle the deserialization of "delegate registration" data.

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| ByteBuffer | buf | Yes | Buffer |

#### Return Value

`void`

## Crypto\Transactions\Types\Transaction

### `id()`

```typescript
public get id()
```

Convert the byte representation to a unique identifier.

#### Return Value

`string`

### `types()`

```typescript
public get types()
```

Check the transaction type.

#### Return Value

`TransactionTypes`

### `verified()`

```typescript
public get verified()
```

Check if the transaction is verified.

#### Return Value

`boolean`

### `getSchema()`

```typescript
public static getSchema()
```

Get transaction schema.

#### Return Value

`TransactionSchema`

### `serialize()`

```typescript
public abstract serialize()
```

Perform AIP11 compliant serialization.

#### Return Value

`ByteBuffer`

### `deserialize()`

```typescript
public abstract deserialize(buf: ByteBuffer)
```

Perform AIP11 compliant deserialization.

#### Return Value

`void`

### `verify()`

```typescript
public verify()
```

Verify the transaction.

#### Return Value

`boolean`

### `verifySecondSignature()`

```typescript
public verifySecondSignature(publicKey: string)
```

Verify the transaction with a second public key.

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| string | publicKey | Yes | Second public key |

#### Return Value

`boolean`

### `verifySchema()`

```typescript
public verifySchema()
```

Verify transaction schema.

#### Return Value

`ISchemaValidationResult`

### `toJson()`

```typescript
public toJson()
```

Convert the transaction to its JSON representation.

#### Return Value

`ITransactionJson`

### `hasVendorField()`

```typescript
public hasVendorField()
```

Verify if the transaction contains a vendorfield.

#### Return Value

`boolean`

## Crypto\Transactions\Types\Transfer

### `getSchema()`

```typescript
public static getSchema()
```

Get transaction schema.

#### Return Value

`schemas.TransactionSchema`

### `hasVendorField()`

```typescript
public hasVendorField()
```

Verify if the transaction contains a vendorfield.

#### Return Value

`boolean`

### `serialize()`

```typescript
public serialize(options?: ISerializeOptions)
```

Perform AIP11 compliant serialization.

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| ISerializeOptions | options | No | Options |

#### Return Value

`ByteBuffer`

### `deserialize()`

```typescript
public deserialize(buf: ByteBuffer)
```

Perform AIP11 compliant deserialization.

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| ByteBuffer | buf | Yes | ... |

#### Return Value

`void`

## Crypto\Transactions\Types\Vote

### `getSchema()`

```typescript
public static getSchema()
```

Get transaction schema.

#### Return Value

`schemas.TransactionSchema`

### `serialize()`

```typescript
public serialize(options?: ISerializeOptions)
```

Perform AIP11 compliant serialization.

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| ISerializeOptions | options | No | ... |

#### Return Value

`ByteBuffer`

### `deserialize()`

```typescript
public deserialize(buf: ByteBuffer)
```

Perform AIP11 compliant deserialization.

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| ByteBuffer | buf | Yes | ... |

#### Return Value

`void`

## Crypto\Transactions\Deserializer

### `deserialize()`

```typescript
public deserialize(serialized: string | Buffer)
```

Perform AIP11 compliant deserialization.

#### Parameters

| Type | Name | Required | Description |  |
| :--- | :--- | :--- | :--- | :--- |
| string | Buffer | serialized | No | Buffer |

#### Return Value

`ITransaction`

### `applyV1Compatibility()`

```typescript
public applyV1Compatibility(transaction: ITransactionData)
```

Apply V1 compatibility on the given transaction.

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| ITransactionData | transaction | No | Transaction |

#### Return Value

`void`

## Crypto\Transactions\Serializer

### `getBytes()`

```typescript
public static getBytes(transaction: ITransactionData, options?: ISerializeOptions)
```

Convert the transaction to its byte representation.

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| ITransactionData | transaction | Yes | Transaction |
| ISerializeOptions | options | No | Options |

#### Return Value

`Buffer`

### `serialize()`

```typescript
public static serialize(transaction: ITransaction, options: ISerializeOptions = {})
```

Perform AIP11 compliant serialization.

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| ITransaction | transaction | Yes | Transaction |
| ISerializeOptions | options | No | Options |

#### Return Value

`Buffer`

## Crypto\Transactions\Signer

### `sign()`

```typescript
public static sign(transaction: ITransactionData, keys: IKeyPair, options?: ISerializeOptions)
```

Sign the given transaction with the provided keys.

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| ITransactionData | transaction | Yes | Transaction |
| IKeyPair | keys | Yes | Keys |
| ISerializeOptions | options | No | Options |

#### Return Value

`string`

### `secondSign()`

```typescript
public static secondSign(transaction: ITransactionData, keys: IKeyPair)
```

Second sign the given transaction with the provided keys.

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| ITransactionData | transaction | Yes | Transaction |
| IKeyPair | keys | Yes | Keys |

#### Return Value

`string`

### `multiSign()`

```typescript
public static multiSign(transaction: ITransactionData, keys: IKeyPair, index: number = -1)
```

Multi sign the given transaction with the provided keys.

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| ITransactionData | transaction | Yes | Transaction |
| IKeyPair | keys | Yes | Keys |
| number | index | No | Index |

#### Return Value

`string`

## Crypto\Transactions\Verifier

### `verify()`

```typescript
public static verify(data: ITransactionData)
```

Verify transaction.

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| ITransactionData | data | Yes | Transaction |

#### Return Value

`boolean`

### `verifySecondSignature()`

```typescript
public static verifySecondSignature(transaction: ITransactionData, publicKey: string)
```

Verify second signature.

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| ITransactionData | data | Yes | Transaction |
| string | publicKey | Yes | Public key |

#### Return Value

`boolean`

### `verifyHash()`

```typescript
public static verifyHash(data: ITransactionData)
```

Verify transaction hash.

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| ITransactionData | data | Yes | Transaction |

#### Return Value

`boolean`

### `verifySchema()`

```typescript
public static verifySchema(data: ITransactionData, strict: boolean = true)
```

Verify transaction schema.

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| ITransactionData | data | Yes | Transaction |
| boolean | strict | No | Strict flag |

#### Return Value

`ISchemaValidationResult`

## Crypto\Crypto\Message

### `sign()`

```typescript
public static sign(message: string, passphrase: string)
```

Sign a message using the given passphrase.

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| string | message | Yes | Message |
| string | passphrase | Yes | Passphrase |

#### Return Value

`IMessage`

### `signWithWif()`

```typescript
public static signWithWif(message: string, wif: string, network?: INetwork)
```

Sign a message using the given WIF string.

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| string | message | Yes | Message |
| string | wif | Yes | Network WIF |
| INetwork | network | No | Network |

#### Return Value

`IMessage`

### `verify()`

```typescript
public static verify({ message, publicKey, signature }: IMessage)
```

Verify the message contents

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| string | message | Yes | Message |
| string | publicKey | Yes | Public key |
| string | signature | Yes | Signature |

#### Return Value

`boolean`

## Crypto\Crypto\Slots

### `getTime()`

```typescript
public static getTime(time?: number)
```

Get the time diff between now and network start.

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| number | time | No | Network start time |

#### Return Value

`number`

### `epoch()`

```typescript
public static getTimeInMsUntilNextSlot()
```

Get in seconds the time before the next slot.

#### Return Value

`number`

### `getSlotNumber()`

```typescript
public static getSlotNumber(epoch?: number)
```

Get the slot number.

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| number | epoch | No | Epoch time |

#### Return Value

`number`

### `getSlotTime()`

```typescript
public static getSlotTime(slot: number)
```

Get the slot time.

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| number | slot | Yes | Slot |

#### Return Value

`number`

### `getNextSlot()`

```typescript
public static getNextSlot()
```

Get the next slot.

#### Return Value

`number`

### `isForgingAllowed()`

```typescript
public static isForgingAllowed(epoch?: number)
```

Verify is forging is allowed.

#### Parameters

| Type | Name | Required | Description |
| :--- | :--- | :--- | :--- |
| number | epoch | No | Epoch time |

#### Return Value

`boolean`

