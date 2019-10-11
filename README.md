# Introduction

Using ARK SDKs, developers can employ the programming language of their choice to build applications utilizing the ARK blockchain. **The ARK SDKs are split into two packages for each language: Client and Cryptography.**

**Client** SDKs help developers fetch information from the ARK blockchain about its current state: which delegates are currently forging, what transactions are associated with a given wallet, and so on.

**Cryptography** SDKs, by contrast, assist developers in working with transactions: signing, serializing, deserializing, etc.

If your application doesn't involve sending transactions, you can most likely build your application using the Client SDK alone. Otherwise, applications looking to leverage the full spectrum of ARK APIs should make use of both Client and Cryptography SDKs.

Usage guides are included for each supported language, and examples of how to use these libraries can be found in the **Examples** section of each.

## Supported Languages & Frameworks

| Crypto | Client | Frameworks |
| :--- | :--- | :--- |
| [TypeScript](/typescript/crypto/) | [TypeScript](/typescript/client/) |  |
| [Java](/java/crypto/) | [Java](/java/client/) |  |
| [PHP](/php/crypto/) | [PHP](/php/client/) |  |
| [Python](/python/crypto/) | [Python](/python/client/) |  |
| [C++](c++/crypto/) | [C++](c++/client/) | [Laravel](/laravel/) |
| [Elixir](elixir/crypto/) | [Elixir](/elixir/client) | [Symfony](/symfony/ |
| [Golang](/golang/crypto/) | [Golang](/golang/client/) |  |
| [.NET](/dotnet/crypto/) | [.NET](/dotnet/client/) |  |
| [Ruby](/ruby/crypto/) | [Ruby](/ruby/client/) |  |
| [Rust](/rust/crypto/) | [Rust](/rust/client/) |  |
| [Swift](/swift/crypto/) | [Swift](/swift/client/) |  |

## Contributing

Contributions to our SDK follow the same guidelines as our general [contribution guidelines](https://docs.ark.io/guidebook/contribution-guidelines/contributing.html).

Additionally to those there are guidelines for the structure of SDKs and what functionality they should provide. Take a look at the [Crypto](https://github.com/ArkEcosystem/gitbooks-sdk/tree/fcb399a02301c4ed91f0da34e9adbad8e0d2f3dc/guidelines/crypto/README.md) and [Client](https://github.com/ArkEcosystem/gitbooks-sdk/tree/fcb399a02301c4ed91f0da34e9adbad8e0d2f3dc/guidelines/client/README.md) guidelines before you start to contribute to make sure the feature or change you plan to implement is in line with those.

