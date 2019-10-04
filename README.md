# Introduction

Using ARK SDKs, developers can employ the programming language of their choice to build applications utilizing the ARK blockchain. **The ARK SDKs are split into two packages for each language: Client and Cryptography.**

**Client** SDKs help developers fetch information from the ARK blockchain about its current state: which delegates are currently forging, what transactions are associated with a given wallet, and so on.

**Cryptography** SDKs, by contrast, assist developers in working with transactions: signing, serializing, deserializing, etc.

If your application doesn't involve sending transactions, you can most likely build your application using the Client SDK alone. Otherwise, applications looking to leverage the full spectrum of ARK APIs should make use of both Client and Cryptography SDKs.

Usage guides are included for each supported language, and examples of how to use these libraries can be found in the **Examples** section of each.

## Supported Languages & Frameworks

| Crypto | Client | Frameworks |
| :--- | :--- | :--- |
| [C++](https://github.com/ArkEcosystem/gitbooks-sdk/tree/fcb399a02301c4ed91f0da34e9adbad8e0d2f3dc/cpp/crypto/getting-started/README.md) | [C++](https://github.com/ArkEcosystem/gitbooks-sdk/tree/fcb399a02301c4ed91f0da34e9adbad8e0d2f3dc/cpp/client/getting-started/README.md) | [Laravel](https://github.com/ArkEcosystem/gitbooks-sdk/tree/fcb399a02301c4ed91f0da34e9adbad8e0d2f3dc/php/frameworks/laravel/README.md) |
| [Elixir](https://github.com/ArkEcosystem/gitbooks-sdk/tree/fcb399a02301c4ed91f0da34e9adbad8e0d2f3dc/elixir/crypto/getting-started/README.md) | [Elixir](https://github.com/ArkEcosystem/gitbooks-sdk/tree/fcb399a02301c4ed91f0da34e9adbad8e0d2f3dc/elixir/client/getting-started/README.md) | [Symfony](https://github.com/ArkEcosystem/gitbooks-sdk/tree/fcb399a02301c4ed91f0da34e9adbad8e0d2f3dc/php/frameworks/symfony/README.md) |
| [Golang](https://github.com/ArkEcosystem/gitbooks-sdk/tree/fcb399a02301c4ed91f0da34e9adbad8e0d2f3dc/golang/crypto/getting-started/README.md) | [Golang](https://github.com/ArkEcosystem/gitbooks-sdk/tree/fcb399a02301c4ed91f0da34e9adbad8e0d2f3dc/golang/client/getting-started/README.md) |  |
| [Java](https://github.com/ArkEcosystem/gitbooks-sdk/tree/fcb399a02301c4ed91f0da34e9adbad8e0d2f3dc/java/crypto/getting-started/README.md) | [Java](https://github.com/ArkEcosystem/gitbooks-sdk/tree/fcb399a02301c4ed91f0da34e9adbad8e0d2f3dc/java/client/getting-started/README.md) |  |
| [.NET](https://github.com/ArkEcosystem/gitbooks-sdk/tree/fcb399a02301c4ed91f0da34e9adbad8e0d2f3dc/dotnet/crypto/getting-started/README.md) | [.NET](https://github.com/ArkEcosystem/gitbooks-sdk/tree/fcb399a02301c4ed91f0da34e9adbad8e0d2f3dc/dotnet/client/getting-started/README.md) |  |
| [PHP](https://github.com/ArkEcosystem/gitbooks-sdk/tree/fcb399a02301c4ed91f0da34e9adbad8e0d2f3dc/php/crypto/getting-started/README.md) | [PHP](https://github.com/ArkEcosystem/gitbooks-sdk/tree/fcb399a02301c4ed91f0da34e9adbad8e0d2f3dc/php/client/getting-started/README.md) |  |
| [Python](https://github.com/ArkEcosystem/gitbooks-sdk/tree/fcb399a02301c4ed91f0da34e9adbad8e0d2f3dc/python/crypto/getting-started/README.md) | [Python](https://github.com/ArkEcosystem/gitbooks-sdk/tree/fcb399a02301c4ed91f0da34e9adbad8e0d2f3dc/python/client/getting-started/README.md) |  |
| [Ruby](https://github.com/ArkEcosystem/gitbooks-sdk/tree/fcb399a02301c4ed91f0da34e9adbad8e0d2f3dc/ruby/crypto/getting-started/README.md) | [Ruby](https://github.com/ArkEcosystem/gitbooks-sdk/tree/fcb399a02301c4ed91f0da34e9adbad8e0d2f3dc/ruby/client/getting-started/README.md) |  |
| [Rust](https://github.com/ArkEcosystem/gitbooks-sdk/tree/fcb399a02301c4ed91f0da34e9adbad8e0d2f3dc/rust/crypto/getting-started/README.md) | [Rust](https://github.com/ArkEcosystem/gitbooks-sdk/tree/fcb399a02301c4ed91f0da34e9adbad8e0d2f3dc/rust/client/getting-started/README.md) |  |
| [Swift](https://github.com/ArkEcosystem/gitbooks-sdk/tree/fcb399a02301c4ed91f0da34e9adbad8e0d2f3dc/swift/crypto/getting-started/README.md) | [Swift](https://github.com/ArkEcosystem/gitbooks-sdk/tree/fcb399a02301c4ed91f0da34e9adbad8e0d2f3dc/swift/client/getting-started/README.md) |  |
| [TypeScript](https://github.com/ArkEcosystem/gitbooks-sdk/tree/fcb399a02301c4ed91f0da34e9adbad8e0d2f3dc/typescript/crypto/getting-started/README.md) | [TypeScript](https://github.com/ArkEcosystem/gitbooks-sdk/tree/fcb399a02301c4ed91f0da34e9adbad8e0d2f3dc/typescript/client/getting-started/README.md) |  |

## Contributing

Contributions to our SDK follow the same guidelines as our general [contribution guidelines](https://docs.ark.io/guidebook/contribution-guidelines/contributing.html).

Additionally to those there are guidelines for the structure of SDKs and what functionality they should provide. Take a look at the [Crypto](https://github.com/ArkEcosystem/gitbooks-sdk/tree/fcb399a02301c4ed91f0da34e9adbad8e0d2f3dc/guidelines/crypto/README.md) and [Client](https://github.com/ArkEcosystem/gitbooks-sdk/tree/fcb399a02301c4ed91f0da34e9adbad8e0d2f3dc/guidelines/client/README.md) guidelines before you start to contribute to make sure the feature or change you plan to implement is in line with those.

