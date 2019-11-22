---
id: getting-started
title: Getting Started
description: Java Crypto Library For Working With Transactions
---

# Crypto

## Install Package via Gradle

> Gradle is an open-source build automation tool that is designed to be flexible enough to build almost any type of software.

To install Gradle on your operating system, follow [this guide](https://gradle.org/install/).

[More detailed guide on Gradle](https://docs.gradle.org/current/userguide/getting_started.html).

```bash
compile group: 'org.arkecosystem.crypto', name: 'crypto', version: '0.1.2'
```

## Install Package via Maven

> Maven is a build automation tool used primarily for Java projects.

To install Maven on your operating system, follow [this guide](https://maven.apache.org/install.html).

[More detailed guide on Maven](https://maven.apache.org/guides/getting-started/maven-in-five-minutes.html).

Once installed, you can edit the `pom.xml` file of the project and add the following values :

```markup
<dependency>
  <groupId>org.arkecosystem</groupId>
  <artifactId>crypto</artifactId>
  <version>0.1.2</version>
</dependency>
```

## Development

1. Fork the [package](https://github.com/ARKEcosystem/java-crypto).
2. Clone forked repository.

   ```bash
   git clone https://github.com/<githubusername>/java-crypto
   ```

3. Next, move into the fresh cloned directory.

   ```bash
   cd java-crypto
   ```

4. Dependencies are now installed, you can now run the tests to see if everything is running as it should.

With Maven

```bash
   mvn test
```

With Gradle

```bash
   gradle test
```

