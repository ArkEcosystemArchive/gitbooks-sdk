---
id: getting-started
title: Getting Started
description: Java Client Library For Communicating With Core Server Public REST API
---

# Client

## Install Package via GitHub Package Repository

**Package is available here:**

{% embed url="https://github.com/ArkEcosystem/java-client/packages/130520" %}

Follow instructions for **Gradle** or **Maven** on how to add project to your source control.

### Gradle

Add this to your **build.gradle** file:

```java
implementation 'org.arkecosystem:client:1.2.9'
```

Execute the following command:

```bash
gradle build
```

### Maven

Add this to **pom.xml** file:

```markup
<dependency>
  <groupId>org.arkecosystem</groupId>
  <artifactId>java-client</artifactId>
  <version>1.2.9</version>
</dependency> 
```

Execute the following command:

```bash
mvn install
```

## Development

1. Fork the [package](https://github.com/ARKEcosystem/java-client).
2. Clone forked repository.

   ```bash
   git clone https://github.com/<githubusername>/java-client
   ```

3. Next, move into the fresh cloned directory.

   ```bash
   cd java-client
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

