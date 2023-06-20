# Introduction

The Onqlave Encryption Engine (OE2) is a set of infrastructure and SDKs provided to you as a service, letting you easily and efficiently encrypt sensitive data in your platform before it leaves your security boundaries. The Onqlave Encryption Engine (OE2) provides you with a state of the art cloud agnostic key management solution which simplifies the daunting task of managing your encryption keys whilst providing you with the best practices when it comes to protecting your sensitive data. You specify which primitive you would like to use based on your use case and leave the rest to us. We manage the master encryption key, issue data encryption keys, wrap them with proper keys without storing any of the keys on our platform. You then use our provided SDKs which securely connect to our infrastructure to get the keys, and encrypt and sign to ensure the authenticity of your data. Using our technology helps ensure that your plaintext data isn’t available to any third party, including Onqlave, your cloud or infrastructure provider.

This developer guide provides a conceptual overview of the Onqlave Encryption Engine (OE2), including an introduction to its architecture, details about how it protects your data, how it differs from server-side encryption, and guidance on selecting critical components for your application to help you get started.

<!-- ## Table of Contents

- [Introduction](#introduction)
- [Table of Contents](#table-of-contents)
  - [Benefit](#benefits)
  - [Concepts](#concepts)
    - [Envelope encryption](#envelope-encryption)
    - [Data encryption key](#data-encryption-key)
    - [Master encryption key](#master-encryption-key)
    - [Symmetric and asymmetric encryptioncrypt](#symmetric-and-asymmetric-encryption)
    - [Polymorphic encryption](#polymorphic-encryption)
    - [Encryption primitives](#encryption-primitives)
  - [How it works](#how-it-works)
  - [Reporting a Vulnerability](#reporting-a-vulnerability) -->
  
## Benefits

The Onqlave Encryption Engine (OE2) has the following benefits:

- **Designed especially for security and ease of use**. You don’t need to be a cryptography expert to use the Onqlave Encryption Engine (OE2). The implementations include helper methods that are designed to work with your existing applications. After you create and configure the required components, the SDKs transparently encrypts and signs your data before you store them in your storage, and verifies and decrypts them when you retrieve them.

- **Designed to be infrastructure and cloud agnostic**. When you use the Onqlave Encryption Engine (OE2), you are not bound to a specific cloud provider or specific implementation by a cloud provider as it is delivered as a service (think of it as any other `software as a service` you use). you can integrate it with any application, whether in cloud or on-premise, developed in any technology of your choice. We are building SDKs for majority of the mainstream programming languages.

- **Includes secure encryption and signing**. The Onqlave Encryption Engine (OE2) includes secure implementations that encrypt your data using a unique data encryption key, and then sign data to protect it against unauthorised changes.

- **Uses cryptographic materials provided by the Onqlave platform**.  The Onqlave Encryption Engine (OE2) uses Onqlave crypto infrastructure to generate, encrypt, and decrypt the unique data encryption key that protects your sensitive data. We automatically issue wrapping keys that encrypt that data key. The Onqlave Encryption Engine (OE2) frees you from cloud restriction as it doesn't require an AWS, GCP or Azure account or any service provided by them.

- **Support for cryptographic materials caching (coming soon)**. The Onqlave Encryption Engine (OE2) provides a bespoke key caching solution that reduces the number of calls to our infrastructure. It allows you to protect your cryptographic materials under a symmetric encryption key without calling Onqlave infrastructure every time you encrypt or decrypt data. This is a good choice for applications that need to minimise latency in their encryption process.

- **Format Preserving Encryption (FPE) (coming soon)**. You can design databases that can search encrypted records without decrypting the entire database. Depending on your threat model and requirements, you can use FPE to perform exact match searches or more customised complex queries on your encrypted database.

- **Support for multitenant database schemas**. The Onqlave Encryption Engine (OE2) enables you to protect data stored in your platform by isolating each tenant with distinct encryption materials. If you have multiple customers performing encrypt operations within your platform, use different Onqlave Arx to provide each customer with a distinct material to use in their cryptographic operations.

- **End-to-end encryption**. Everything in your Onqlave Encryption Engine (OE2) account is always end-to-end encrypted. This makes it impossible for someone to learn anything by intercepting your data while it’s in transit or even obtaining it from Onqlave.

- **256-bit AES encryption**. Your data is kept safe by `AES-GCM-256 authenticated encryption` on the Onqlave Encryption Engine (OE2). The data you entrust to Onqlave is effectively impossible to decrypt.

- **Secure random numbers**. Encryption keys, initialization vectors, and nonces are all generated using `cryptographically secure pseudorandom number generators`.

- **Principled privacy policy**. The Onqlave Encryption Engine (OE2) was designed with a deep respect for your privacy. Any information you share with us is only ever used to provide you with service and support.

## Concepts

This topic explains the concepts and terminology used in the Onqlave Encryption Engine (OE2).

### Envelope encryption

Storing and encrypting data at scale requires using a central cryptographic key management service with multiple layers of keys for the encrypted data. An example of multiple layer of keys is envelope encryption, which is the process of encrypting a key with another key. The Onqlave Encryption Engine (OE2) uses [Master encryption keys (MEK)](#master-encryption-key) to protect [Data encryption keys](#data-encryption-key). The Onqlave Encryption Engine (OE2) uses [Polymorphic encryption](#polymorphic-encryption) to ensure that every encryption gets its own unique [Data encryption keys](#data-encryption-key).

### Data encryption key

A data encryption key is an encryption key that the Onqlave Encryption Engine (OE2) SDK uses to encrypt the data. Each data encryption key is a byte array that conforms to the encryption method of your Onqlave Arx. You don't need to specify, generate, implement, extend, protect, or use data encryption keys. The Onqlave Encryption Engine (OE2) implicitly does that work for you when you call the encrypt and decrypt operations.

### Master encryption key

A Master encryption key, also known as key encryption key is a key that the Onqlave Encryption Engine (OE2) uses to encrypt the [Data encryption keys](#data-encryption-key) that encrypts your data.

### Symmetric and asymmetric encryption

Symmetric encryption uses the same key to encrypt and decrypt data. Asymmetric encryption uses a mathematically related data key pair. One key in the pair encrypts the data; only the other key in the pair can decrypt the data. The Onqlave Encryption Engine (OE2) uses envelope encryption. It encrypts your data with a symmetric data key. It encrypts the symmetric data key with one or more symmetric or asymmetric wrapping keys.

- **Encrypting your data (symmetric encryption)**: To encrypt your data, the Onqlave Encryption Engine (OE2) SDK uses a symmetric data key and an algorithm specified by your configuration of Onqlave Arx that includes a symmetric encryption algorithm. To decrypt the data, the Onqlave Encryption Engine (OE2) SDK uses the same data key and the same algorithm suite.

### Polymorphic encryption

The Onqlave Encryption Engine (OE2) makes sure every encryption operation gets its own unique [Data encryption key](#data-encryption-key) to preserve the security and privacy of your data. The technique is called `Polymorphic encryption`.

### Encryption primitives

Authenticated Encryption (AE) is an encryption scheme which simultaneously assures the data confidentiality (also known as privacy: encrypted message is impossible to understand without the knowledge of a secret key) and authenticity (it is unforgeable the encrypted message includes an authentication tag that the sender can calculate only if she possesses secret key). Examples of encryption modes that provide AE are GCM, CCM. The Onqlave Encryption Engine (OE2) and extended version of AE called Authenticated Encryption with Additional Data (AEAD) in order to create [Data encryption keys](#data-encryption-key). Additional Authenticated Data (AAD) is bound to the encrypted data, because you cannot decrypt the ciphertext unless you know the AAD, but it is not stored as part of the ciphertext. AAD also does not increase the cryptographic strength of the ciphertext. Instead it is an additional check by The Onqlave Encryption Engine (OE2) SDK to authenticate a decryption request. The Onqlave Encryption Engine (OE2) SDK uses Authenticated Encryption with Additional Data (AEAD) for all encryption operations, so that it guarantees the confidentiality as well as the integrity of the keys provided for each tenant.  

## How it works

As explained in the [Introduction](#introduction), The Onqlave platform is comprised of two major parts: The Onqlave Encryption Engine (OE2) which is responsible for managing your keys, and The Onqlave Encryption Engine (OE2) SDK which is used to integrate OE2 with your applications.  

The Onqlave Encryption Engine (OE2) SDK provides client-side encryption libraries that are designed specifically to protect your sensitive data. The libraries include secure implementations that you can extend or use unchanged. For more information about using SDKs, see our SDK [documentation](https://docs.onqlave.com/guides/sdks/sdk-node/) for your programming language.

The workflows in this section explain how the Onqlave Encryption Engine (OE2) SDK encrypts and signs and decrypts and verifies the data in your applications. These workflows describe the basic process using abstract elements and the default features. For details about how the Onqlave Encryption Engine (OE2) SDK works with your programming language, see our GitHub repositories.

The Onqlave Encryption Engine (OE2) SDK uses [envelope encryption](#envelope-encryption) to protect your data. Each record is encrypted under a unique [data encryption key](#data-encryption-key) provided by the Onqlave platform. To decrypt the encrypted record, the Onqlave Encryption Engine (OE2) SDK communicates with the Onqlave platform to decrypt the data encryption key using the [master encryption keys](#master-encryption-key) assigned to the Onqlave Arx. Then it can decrypt the ciphertext and return a plaintext entry.

For more information about the terms used in the Onqlave Encryption Engine, see [Concepts](#concepts).

### Encrypt and sign

At its core, the Onqlave Encryption Engine (OE2) SDK is a record encryptor that encrypts, signs, verifies, and decrypts the records in your dataset. It gets the encryption materials, and instructions on how to use them, from the Onqlave platform and uses them to encrypt the data.

The following walkthrough describes how the Onqlave Encryption Engine (OE2) SDK encrypts and signs your data entries.

1. The Onqlave platform provides the Onqlave Encryption Engine (OE2) SDK with unique data encryption key: one wrapped data encryption key, a copy of the data key encrypted wrapped in an ephemeral encrypted asymmetric key.
2. The encryption method encrypts data you specified.
3. The encryption method encapsulates the encrypted data encryption key, algorithm information and the actual cipher data in a data encryption packet.
4. The encryption method signs the data encyption packet using additional data provided by you.
5. The encryption method returns the encrypted and signed cipher packet to the caller.  

### Decrypt and verify

1. The decryption method extracts the encrypted data encryption key from cipher packet.
2. The decryption method extracts the encryption algorithm including initialisation vector and tags
3. The decryption method contacts the Onqlave platform to decrypt the encrypted data encryption key.
4. The Onqlave platform returns the data encryption key, wrapped in an ethemeral encrypted assymetric key.
5. The decryption method identifies the data in the cipher packet received as input.
6. The decryption method unwraps the data encryption key, and use it to decrypt the data.
7. The decryption method verifies the integrity of the data using additional data provided by you.
8. The decryption method returns the decrypted and verified plain data to the caller.  

## Reporting a Vulnerability

If you discover a potential security issue in this project, please reach out to us at <security@onqlave.com>. Please do not create public GitHub issues or Pull Requests, as malicious actors could potentially view them.
