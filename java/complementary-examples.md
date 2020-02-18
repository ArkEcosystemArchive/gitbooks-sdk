---
description: >-
  Complementary Examples of how the Crypto SDK can combined with the Client SDK
  to get your transactions out to the network and verified.
---

# Complementary Examples

## Creating and Broadcasting a Transfer

```java
import com.google.gson.internal.LinkedTreeMap;
import org.arkecosystem.client.Connection;
import org.arkecosystem.crypto.configuration.Network;
import org.arkecosystem.crypto.networks.Devnet;
import org.arkecosystem.crypto.transactions.Transaction;
import org.arkecosystem.crypto.transactions.builder.Transfer;

import java.io.IOException;
import java.util.ArrayList;
import java.util.HashMap;

public class TransferTransaction {

    public static void main(String[] args) throws IOException {
        // Set the network
        Network.set(new Devnet());
        // Make configurations and connect to the node
        HashMap<String, Object> configurations = new HashMap<>();
        configurations.put("host", "https://dexplorer.ark.io/api/");
        configurations.put("content-type","application/json");
        Connection connection = new Connection(configurations);

        // Retrieve the nonce
        long nonce = Long.parseLong(((LinkedTreeMap<String, Object>) connection.api()
                .wallets
                .show("YOUR_SENDER_WALLET_ADDRESS")
                .get("data"))
                .get("nonce")
                .toString());
        // Increment it by one
        nonce++;

        // Create the transaction
        Transaction actual = new Transfer()
                .recipient("Address of Recipient")
                .amount(10^8) // amount of arktoshis
                .vendorField("Hello world")
                .nonce(nonce)
                .sign("this is a top secret passphrase")
                .transaction;

        // Add transaction to payload
        ArrayList<HashMap> payload = new ArrayList<>();
        payload.add(actual.toHashMap());

        // Broadcast the transaction
        LinkedTreeMap<String, Object> broadcastResponse = connection.api().transactions.create(payload);

        // Log the response
        System.out.println(broadcastResponse);

    }
}
```

{% hint style="info" %}
The vendorField is optional and limited to a length of 255 characters. It can be a good idea to add a vendor field to your transactions if you want to be able to easily track them in the future.
{% endhint %}

## Creating and Broadcasting a Second Signature <a id="creating-and-broadcasting-a-second-signature"></a>

```java
import com.google.gson.internal.LinkedTreeMap;
import org.arkecosystem.client.Connection;
import org.arkecosystem.crypto.configuration.Network;
import org.arkecosystem.crypto.networks.Devnet;
import org.arkecosystem.crypto.transactions.Transaction;
import org.arkecosystem.crypto.transactions.builder.SecondSignatureRegistration;

import java.io.IOException;
import java.util.ArrayList;
import java.util.HashMap;

public class SecondSignatureTransaction {

    public static void main(String[] args) throws IOException {
        // Set the network
        Network.set(new Devnet());
        // Make configurations and connect to the node
        HashMap<String, Object> configurations = new HashMap<>();
        configurations.put("host", "https://dexplorer.ark.io/api/");
        configurations.put("content-type","application/json");
        Connection connection = new Connection(configurations);

        // Retrieve the nonce
        long nonce = Long.parseLong(((LinkedTreeMap<String, Object>) connection.api()
                .wallets
                .show("YOUR_SENDER_WALLET_ADDRESS")
                .get("data"))
                .get("nonce").toString());
        // Increment it by one
        nonce++;

        // Create the transaction
        Transaction actual = new SecondSignatureRegistration()
                .signature("this is a top secret second passphrase")
                .nonce(nonce)
                .sign("this is a top secret passphrase")
                .transaction;

        // Add transaction to payload
        ArrayList<HashMap> payload = new ArrayList<>();
        payload.add(actual.toHashMap());

        // Broadcast the transaction
        LinkedTreeMap<String, Object> broadcastResponse = connection.api().transactions.create(payload);

        // Log the response
        System.out.println(broadcastResponse);

    }
}
```

## Creating and Broadcasting a Delegate Registration <a id="creating-and-broadcasting-a-delegate-registration"></a>

```java
import com.google.gson.internal.LinkedTreeMap;
import org.arkecosystem.client.Connection;
import org.arkecosystem.crypto.configuration.Network;
import org.arkecosystem.crypto.networks.Devnet;
import org.arkecosystem.crypto.transactions.Transaction;
import org.arkecosystem.crypto.transactions.builder.DelegateRegistration;

import java.io.IOException;
import java.util.ArrayList;
import java.util.HashMap;

public class DelegateRegistrationTransaction {

    public static void main(String[] args) throws IOException {
        // Set the network
        Network.set(new Devnet());
        // Make configurations and connect to the node
        HashMap<String, Object> configurations = new HashMap<>();
        configurations.put("host", "https://dexplorer.ark.io/api/");
        configurations.put("content-type","application/json");
        Connection connection = new Connection(configurations);

        // Retrieve the nonce
        long nonce = Long.parseLong(((LinkedTreeMap<String, Object>) connection.api()
                .wallets
                .show("YOUR_SENDER_WALLET_ADDRESS")
                .get("data"))
                .get("nonce").toString());
        // Increment it by one
        nonce++;

        // Create the transaction
        Transaction actual = new DelegateRegistration()
                .username("johndoe")
                .nonce(nonce)
                .sign("this is a top secret passphrase")
                .transaction;

        // Add transaction to payload
        ArrayList<HashMap> payload = new ArrayList<>();
        payload.add(actual.toHashMap());

        // Broadcast the transaction
        LinkedTreeMap<String, Object> broadcastResponse = connection.api().transactions.create(payload);

        // Log the response
        System.out.println(broadcastResponse);
        
    }
}
```

## Creating and Broadcasting a Vote

```java
import com.google.gson.internal.LinkedTreeMap;
import org.arkecosystem.client.Connection;
import org.arkecosystem.crypto.configuration.Network;
import org.arkecosystem.crypto.networks.Devnet;
import org.arkecosystem.crypto.transactions.Transaction;
import org.arkecosystem.crypto.transactions.builder.Vote;

import java.io.IOException;
import java.util.ArrayList;
import java.util.HashMap;
import java.util.List;

public class VoteTransaction {
    public static void main(String[] args) throws IOException {
        // Set the network
        Network.set(new Devnet());
        // Make configurations and connect to the node
        HashMap<String, Object> configurations = new HashMap<>();
        configurations.put("host", "https://dexplorer.ark.io/api/");
        configurations.put("content-type","application/json");
        Connection connection = new Connection(configurations);

        // Retrieve the nonce
        long nonce = Long.parseLong(((LinkedTreeMap<String, Object>) connection.api()
                .wallets
                .show("YOUR_SENDER_WALLET_ADDRESS")
                .get("data"))
                .get("nonce").toString());
        // Increment it by one
        nonce++;

        List <String>votes = new ArrayList<>();
        votes.add("+public_key_of_a_delegate_wallet");
        // Create the transaction
        Transaction actual = new Vote()
                .votes(votes)
                .nonce(nonce)
                .sign("this is a top secret passphrase")
                .transaction;

        // Add transaction to payload
        ArrayList<HashMap> payload = new ArrayList<>();
        payload.add(actual.toHashMap());

        // Broadcast the transaction
        LinkedTreeMap<String, Object> broadcastResponse = connection.api().transactions.create(payload);

        // Log the response
        System.out.println(broadcastResponse);

    }
}
```

{% hint style="info" %}
Note the **plus** prefix for the public key that is passed to the **votes** function. This prefix denotes that this is a transaction to remove a vote from the given delegate.
{% endhint %}

## Creating and Broadcasting an Unvote

```java
import com.google.gson.internal.LinkedTreeMap;
import org.arkecosystem.client.Connection;
import org.arkecosystem.crypto.configuration.Network;
import org.arkecosystem.crypto.networks.Devnet;
import org.arkecosystem.crypto.transactions.Transaction;
import org.arkecosystem.crypto.transactions.builder.Vote;

import java.io.IOException;
import java.util.ArrayList;
import java.util.HashMap;
import java.util.List;

public class UnvoteTransaction {
    public static void main(String[] args) throws IOException {
        // Set the network
        Network.set(new Devnet());
        // Make configurations and connect to the node
        HashMap<String, Object> configurations = new HashMap<>();
        configurations.put("host", "https://dexplorer.ark.io/api/");
        configurations.put("content-type", "application/json");
        Connection connection = new Connection(configurations);

        // Retrieve the nonce
        long nonce = Long.parseLong(((LinkedTreeMap<String, Object>) connection.api()
                .wallets
                .show("YOUR_SENDER_WALLET_ADDRESS")
                .get("data"))
                .get("nonce").toString());
        // Increment it by one
        nonce++;

        List<String> votes = new ArrayList<>();
        votes.add("-public_key_of_a_delegate_wallet");
        // Create the transaction
        Transaction actual = new Vote()
                .votes(votes)
                .nonce(nonce)
                .sign("this is a top secret passphrase")
                .transaction;

        // Add transaction to payload
        ArrayList<HashMap> payload = new ArrayList<>();
        payload.add(actual.toHashMap());

        // Broadcast the transaction
        LinkedTreeMap<String, Object> broadcastResponse = connection.api().transactions.create(payload);

        // Log the response
        System.out.println(broadcastResponse);

    }
}

```

{% hint style="info" %}
Note the **minus** prefix for the public key that is passed to the **votes** function. This prefix denotes that this is a transaction to add a vote to the given delegate.
{% endhint %}

## Creating and Broadcasting a IPFS

```java
import com.google.gson.internal.LinkedTreeMap;
import org.arkecosystem.client.Connection;
import org.arkecosystem.crypto.configuration.Network;
import org.arkecosystem.crypto.networks.Devnet;
import org.arkecosystem.crypto.transactions.Transaction;
import org.arkecosystem.crypto.transactions.builder.Ipfs;

import java.io.IOException;
import java.util.ArrayList;
import java.util.HashMap;

public class IpfsTransaction {
    public static void main(String[] args) throws IOException {
        // Set the network
        Network.set(new Devnet());
        // Make configurations and connect to the node
        HashMap<String, Object> configurations = new HashMap<>();
        configurations.put("host", "https://dexplorer.ark.io/api/");
        configurations.put("content-type", "application/json");
        Connection connection = new Connection(configurations);

        // Retrieve the nonce
        long nonce = Long.parseLong(((LinkedTreeMap<String, Object>) connection.api()
                .wallets
                .show("YOUR_SENDER_WALLET_ADDRESS")
                .get("data"))
                .get("nonce").toString());
        // Increment it by one
        nonce++;
        
        // Create the transaction
        Transaction actual = new Ipfs()
                .ipfsAsset("QmR45FmbVVrixReBwJkhEKde2qwHYaQzGxu4ZoDeswuF9w")
                .nonce(nonce)
                .sign("this is a top secret passphrase")
                .transaction;

        // Add transaction to payload
        ArrayList<HashMap> payload = new ArrayList<>();
        payload.add(actual.toHashMap());

        // Broadcast the transaction
        LinkedTreeMap<String, Object> broadcastResponse = connection.api().transactions.create(payload);

        // Log the response
        System.out.println(broadcastResponse);

    }
}

```

## Creating and Broadcasting a Multi Payment

```java
import com.google.gson.internal.LinkedTreeMap;
import org.arkecosystem.client.Connection;
import org.arkecosystem.crypto.configuration.Network;
import org.arkecosystem.crypto.networks.Devnet;
import org.arkecosystem.crypto.transactions.Transaction;
import org.arkecosystem.crypto.transactions.builder.MultiPayment;


import java.io.IOException;
import java.util.ArrayList;
import java.util.HashMap;

public class MultiPaymentTransaction {
    public static void main(String[] args) throws IOException {
        // Set the network
        Network.set(new Devnet());
        // Make configurations and connect to the node
        HashMap<String, Object> configurations = new HashMap<>();
        configurations.put("host", "https://dexplorer.ark.io/api/");
        configurations.put("content-type","application/json");
        Connection connection = new Connection(configurations);

        // Retrieve the nonce
        long nonce = Long.parseLong(((LinkedTreeMap<String, Object>) connection.api()
                .wallets
                .show("YOUR_SENDER_WALLET_ADDRESS")
                .get("data"))
                .get("nonce").toString());
        // Increment it by one
        nonce++;

        // Create the transaction
        Transaction actual = new MultiPayment()
                .addPayment("Address of Recipient Wallet 1", 10^8)
                .addPayment("Address of Recipient Wallet 2", 10^8)
                .addPayment("Address of Recipient Wallet 3", 10^8)
                .nonce(nonce)
                .sign("this is a top secret passphrase")
                .transaction;

        // Add transaction to payload
        ArrayList<HashMap> payload = new ArrayList<>();
        payload.add(actual.toHashMap());

        // Broadcast the transaction
        LinkedTreeMap<String, Object> broadcastResponse = connection.api().transactions.create(payload);

        // Log the response
        System.out.println(broadcastResponse);

    }
}
```

## Creating and Broadcasting a Delegate Resignation

```java
import com.google.gson.internal.LinkedTreeMap;
import org.arkecosystem.client.Connection;
import org.arkecosystem.crypto.configuration.Network;
import org.arkecosystem.crypto.networks.Devnet;
import org.arkecosystem.crypto.transactions.Transaction;
import org.arkecosystem.crypto.transactions.builder.DelegateResignation;

import java.io.IOException;
import java.util.ArrayList;
import java.util.HashMap;

public class DelegateResignationTransaction {
    public static void main(String[] args) throws IOException {
        // Set the network
        Network.set(new Devnet());
        // Make configurations and connect to the node
        HashMap<String, Object> configurations = new HashMap<>();
        configurations.put("host", "https://dexplorer.ark.io/api/");
        configurations.put("content-type","application/json");
        Connection connection = new Connection(configurations);

        // Retrieve the nonce
        long nonce = Long.parseLong(((LinkedTreeMap<String, Object>) connection.api()
                .wallets
                .show("YOUR_SENDER_WALLET_ADDRESS")
                .get("data"))
                .get("nonce").toString());
        // Increment it by one
        nonce++;

        // Create the transaction
        Transaction actual = new DelegateResignation()
                .nonce(nonce)
                .sign("this is a top secret passphrase")
                .transaction;

        // Add transaction to payload
        ArrayList<HashMap> payload = new ArrayList<>();
        payload.add(actual.toHashMap());

        // Broadcast the transaction
        LinkedTreeMap<String, Object> broadcastResponse = connection.api().transactions.create(payload);

        // Log the response
        System.out.println(broadcastResponse);

    }
}

```

{% hint style="info" %}
A delegate resignation has to be sent from the delegate wallet itself to verify its identity.
{% endhint %}

## Creating and Broadcasting a HTLC Lock

```java
import com.google.gson.internal.LinkedTreeMap;
import org.arkecosystem.client.Connection;
import org.arkecosystem.crypto.configuration.Network;
import org.arkecosystem.crypto.enums.HtlcLockExpirationType;
import org.arkecosystem.crypto.networks.Devnet;
import org.arkecosystem.crypto.transactions.Transaction;
import org.arkecosystem.crypto.transactions.builder.HtlcLock;

import java.io.IOException;
import java.util.ArrayList;
import java.util.HashMap;

public class HtlcLockTransaction {
    public static void main(String[] args) throws IOException {
        // Set the network
        Network.set(new Devnet());
        // Make configurations and connect to the node
        HashMap<String, Object> configurations = new HashMap<>();
        configurations.put("host", "https://dexplorer.ark.io/api/");
        configurations.put("content-type","application/json");
        Connection connection = new Connection(configurations);

        // Retrieve the nonce
        long nonce = Long.parseLong(((LinkedTreeMap<String, Object>) connection.api()
                .wallets
                .show("YOUR_SENDER_WALLET_ADDRESS")
                .get("data"))
                .get("nonce").toString());
        // Increment it by one
        nonce++;

        // Create the transaction
        Transaction actual = new HtlcLock()
                .secretHash("0f128d401958b1b30ad0d10406f47f9489321017b4614e6cb993fc63913c5454")
                .expirationType(HtlcLockExpirationType.BLOCK_HEIGHT, 1000)
                .amount(10^8)
                .nonce(nonce)
                .sign("this is a top secret passphrase")
                .transaction;

        // Add transaction to payload
        ArrayList<HashMap> payload = new ArrayList<>();
        payload.add(actual.toHashMap());

        // Broadcast the transaction
        LinkedTreeMap<String, Object> broadcastResponse = connection.api().transactions.create(payload);

        // Log the response
        System.out.println(broadcastResponse);

    }
}

```

## Creating and Broadcasting a HTLC Claim

```java
import com.google.gson.internal.LinkedTreeMap;
import org.arkecosystem.client.Connection;
import org.arkecosystem.crypto.configuration.Network;
import org.arkecosystem.crypto.networks.Devnet;
import org.arkecosystem.crypto.transactions.Transaction;
import org.arkecosystem.crypto.transactions.builder.HtlcClaim;


import java.io.IOException;
import java.util.ArrayList;
import java.util.HashMap;

public class HtlcClaimTransaction {
    public static void main(String[] args) throws IOException {
        // Set the network
        Network.set(new Devnet());
        // Make configurations and connect to the node
        HashMap<String, Object> configurations = new HashMap<>();
        configurations.put("host", "https://dexplorer.ark.io/api/");
        configurations.put("content-type","application/json");
        Connection connection = new Connection(configurations);

        // Retrieve the nonce
        long nonce = Long.parseLong(((LinkedTreeMap<String, Object>) connection.api()
                .wallets
                .show("YOUR_SENDER_WALLET_ADDRESS")
                .get("data"))
                .get("nonce").toString());
        // Increment it by one
        nonce++;

        // Create the transaction
        Transaction actual = new HtlcClaim()
                .htlcClaimAsset(
                        "943c220691e711c39c79d437ce185748a0018940e1a4144293af9d05627d2eb4",
                        "c27f1ce845d8c29eebc9006be932b604fd06755521b1a8b0be4204c65377151a")
                .nonce(nonce)
                .sign("this is a top secret passphrase")
                .transaction;

        // Add transaction to payload
        ArrayList<HashMap> payload = new ArrayList<>();
        payload.add(actual.toHashMap());

        // Broadcast the transaction
        LinkedTreeMap<String, Object> broadcastResponse = connection.api().transactions.create(payload);

        // Log the response
        System.out.println(broadcastResponse);

    }
}

```

{% hint style="info" %}
The **unlockSecret** has to be a SHA256 hash of the plain text secret that you shared with the person that is allowed to claim the transaction.
{% endhint %}

## Creating and Broadcasting a HTLC Refund

```java
import com.google.gson.internal.LinkedTreeMap;
import org.arkecosystem.client.Connection;
import org.arkecosystem.crypto.configuration.Network;
import org.arkecosystem.crypto.networks.Devnet;
import org.arkecosystem.crypto.transactions.Transaction;
import org.arkecosystem.crypto.transactions.builder.HtlcRefund;

import java.io.IOException;
import java.util.ArrayList;
import java.util.HashMap;

public class HtlcRefundTransaction {
    public static void main(String[] args) throws IOException {
        // Set the network
        Network.set(new Devnet());
        // Make configurations and connect to the node
        HashMap<String, Object> configurations = new HashMap<>();
        configurations.put("host", "https://dexplorer.ark.io/api/");
        configurations.put("content-type","application/json");
        Connection connection = new Connection(configurations);

        // Retrieve the nonce
        long nonce = Long.parseLong(((LinkedTreeMap<String, Object>) connection.api()
                .wallets
                .show("YOUR_SENDER_WALLET_ADDRESS")
                .get("data"))
                .get("nonce").toString());
        // Increment it by one
        nonce++;

        // Create the transaction
        Transaction actual = new HtlcRefund()
                .htlcRefundAsset("943c220691e711c39c79d437ce185748a0018940e1a4144293af9d05627d2eb4")
                .nonce(nonce)
                .sign("this is a top secret passphrase")
                .transaction;

        // Add transaction to payload
        ArrayList<HashMap> payload = new ArrayList<>();
        payload.add(actual.toHashMap());

        // Broadcast the transaction
        LinkedTreeMap<String, Object> broadcastResponse = connection.api().transactions.create(payload);

        // Log the response
        System.out.println(broadcastResponse);

    }
}

```

