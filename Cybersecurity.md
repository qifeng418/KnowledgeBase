[Introduction](#introduction)

[Encryption Basics](#encryption)

[Symmetric Encryption (DES to AES)](#symmetric)

[Asymmetric encryption (RSA)](#asymmetric)

[Message Integrity and Authentication](#message)

[Certificate and PKI](#pki)

[User Authenticatoin](#user)

[Firewall and IDS](#ids)

[Software Security](#software)

[Network Security](#networking)

## 📖 Introduction <div id="introduction"></div>

### Q. 3 Classical Security Objectives?
**Confidentiality** (secrecy, privacy): Information is not exposed to unauthorized parties.

**Integrity**: Information is not modified by unauthorized parties.

**Availability**: Information can be accessed by authorized parties at proper time.

### Q. What are Threat, Vulnerability, incident, and Attacks?
**Threat**: Something bad that could happen.

**Vulnerability**: Weakness in an information system that could be exploited.

**Incident**: When a vulnerability is exploited to compromise the security of systems, the result is a security incident.

**Attack**: Some action taken by a malicious intruder (Passive Adversary and Active Adversary).

### Q. What are Moore’s law, Gates’ law, Neumann’s law, Metcalfe’s law, Evan’s Law?
**Moore’s law**: Processing power doubles every 18 months.

**Gates’ law**: Software grows to use all available memory and processing power. (Multics 1970: ~55k lines of code; Windows 2000: ~55M lines of code)

**Neumann’s law**: Number of bugs increases as square of code size. Number of vulnerabilities is approximately linear in the number of program bugs.

**Metcalfe’s law**: Value of a network is square of number of users.

**Evan’s Law**: Security risk is the product of the number of vulnerabilities and the value of network.

### Q. Why is defense so hard (Principle of Easiest Penetration)?
An intruder only needs to find **one** vulnerability while defender needs to control **all** possible vulnerabilities.

### Q. How to achieve security (control)?
**Policy** (What we are trying to protect); **Mechanism** (How to enforce the security policy); **Assurance** (How well the security mechanism enforces the policy).

### Q. What is Kerckhoffs Principle?
Only the key should be kept secret, while the algorithm itself should be publicly known.

### Q. What are Security Tradeoffs?
Cost and Mateinance, Efficiency and User Experience, Risk and Compliance.

## 📖 Encryption Basics <div id="encryption"></div>

### Q. What is Cryptography, Cryptology, Encryption, Decryption, Cryptosystem, Cryptographer, Cryptanalyst?
**Cryptography**, or **cryptology** is the practice and study of techniques for secure communication.

**Encryption** is the process of encoding information. This process converts the original representation of the information, known as plaintext, into an alternative form known as ciphertext. Only authorized parties can decipher a ciphertext back to plaintext and access the original information.

**Decryption** is generally the reverse process of encryption. It is the process of decoding the data which has been encrypted into a secret format.

**Cryptographers** secure computer and information technology systems by creating algorithms and ciphers to encrypt data. Cryptographers also analyze existing encryption systems to identify weaknesses and vulnerabilities. They develop and test cryptology theories and techniques, implementing new or revamped encryption solutions.

**Cryptosystem** is a suite of cryptographic algorithms needed to implement a particular security service, most commonly for achieving confidentiality. Typically, a cryptosystem consists of three algorithms: one for key generation, one for encryption, and one for decryption.

**Cryptanalysts** understand how to decipher secret codes and write codes that cannot be cracked by hackers. 

### Q. What is Symmetric Cryptosystem?
In an encryption system the sender and receiver of a message share **a single, common key** that is used to encrypt and decrypt the message.

### Q. Scenarios of cryptanalysis?

| Scenarios | Explanation |
| --- | --- |
| Ciphertext only | Cryptanalyst knows ciphertext only |
| Known plaintext | Cryptanalyst happens to know some plaintext-ciphertext pairs |
| Chosen plaintext | Cryptanalyst knows some plaintext-ciphertext pairs for selected plaintext |
| Chosen ciphertext | Cryptanalyst knows some plaintext-ciphertext pairs for selected ciphertext |

### Q. List 3 kinds of classical ciphers.
Caesar Cipher; Vigenere cipher; One-time pad

### Q. What is Substitution Cipher and its weakness?
A substitution cipher maps each plaintext letter to a unique ciphertext letter. It can be trivially broken for known plaintext attack and easily broken for ciphertext only attack.

### Q. Features (why secure and its limitations) of One-Time Pad.
One-Time Pad (Vernam Cipher) is an encryption technique that cannot be cracked, but requires the use of a one-time pre-shared key the same size as, or longer than, the message being sent. In encryption, the plaintext is XORed with the key to get cipher text, while in decryption, the cipher text is XORed again with the key to get plaintext.

The resulting ciphertext will be impossible to decrypt or break if the following four conditions are met:

1) The key must be **truly random**.
2) The key must be at least **as long as** the plaintext.
3) The key must never be **reused** in whole or in part
4) The key must be kept completely secret. (**Distribuion**)

But it is impractical because true random number generator is hard to achieve, and Key must be at least as long as plaintext. Also Key distribution is hard to be totally secret.

### Q. What is Permutation Cipher and its weakness?
Permutation Cipher rearranges the letters of the message. There is high space cost and long delay in encipherment and decipherment.

### Q. What are confusion and diffusion?
They are two Concepts related to encryption strength.

**Confusion** refers to making it difficult for a crytanalyst to determine how a message and key were transformed into ciphertext. It refers to the complexity of the functional relationship between the plaintext/key pair and the ciphertext.

**Diffusion** refers to widely spreading the information from the message or the key across the ciphertext. It refers to the information distribution of a single plaintext symbol over the entire output.

### Q. What is product cipher?
It refers to the combinations and iterations of substitution and permutation.

### Q. Is product cipher more secure?
Hard to say. Applying two ciphers does not necessarily mean the result is any stronger than, or even as strong as, either individual cipher.

### Q. Shannon’s characteristics of good ciphers.
1) Amount of secrecy determines amount of labor.
2) Set of keys and enciphering algorithm are simple.
3) Implementation of process is simple.
4) Errors do not propagate.
5) Size of cipher text is no larger than original message.

### Q. Properties of “Trustworthy” encryption systems.
1) It must be satisfied for commercial users to select.
2) It is based on sound mathematics.
3) It has been analyzed by competent experts and found to be sound.
4) It has stood the “test of time”.

### Q. What are the 3 popular algorithms in the commercial world?
1) DES (data encryption standard)
2) AES (advanced encryption standard)
3) RSA (Rivest-Shamir-Adelman)

### Q. What are computational security and unconditional security?
**Computationally secure** means The encryption algorithm has been proven through mathematical analysis to resist any “shortcuts” which allow recovery of plain text from the cipher text.

**Unconditionally secure** means no amount of computer power can recover the plain text given the cipher text.

## 📖 Symmetric Encryption (DES to AES) <div id="symmetric"></div>

### Q. What is Block Cipher?
A block cipher is an encryption method that applies a **deterministic algorithm** along with a symmetric key to encrypt a block of text, rather than encrypting one bit at a time as in stream ciphers.

### Q. What is initialization vector?
An initialization vector is a block of bits that is used by several modes to randomize the encryption and hence to produce distinct ciphertexts.

An initialization vector has different security requirements than a key, so the IV usually does not need to be secret. However, in most cases, it is important that an initialization vector is **never reused under the same key**. For CBC and CFB, reusing an IV leaks some information about the first block of plaintext, and about any common prefix shared by the two messages. If we forget the IV value, we can mostly recover all blocks, except the first block.

### Q. What is ECB(Electronic Codebook) and its disadvantages?
ECB is a kind of Block Cipher.

<img src="https://images.slideplayer.com/39/10983426/slides/slide_3.jpg" height="400" width="600" />

The disadvantage of this method is **a lack of diffusion**. Because ECB encrypts identical plaintext blocks into identical ciphertext blocks, it does not hide data patterns well. ECB is not recommended for use in cryptographic protocols.

### Q. What is CBC(Cipher Block Chaining)?
CCB is a kind of Block Cipher. In CBC mode, each block of plaintext is XORed with the previous ciphertext block before being encrypted. This way, each ciphertext block depends on all plaintext blocks processed up to that point. To make each message unique, an initialization vector must be used in the first block.

<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/8/80/CBC_encryption.svg/600px-CBC_encryption.svg.png" height="200" width="500" />
<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/2/2a/CBC_decryption.svg/600px-CBC_decryption.svg.png" height="200" width="500" />

Example:

<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/3/3a/CBC_example_v3.svg/800px-CBC_example_v3.svg.png" height="180" width="300" />
<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/2/2a/Rev_CBC_example_v3.svg/800px-Rev_CBC_example_v3.svg.png" height="180" width="300" />

Disadvantages of CBC are:
1) Chain Dependency: proper decryption requires a correct preceding cipher block.
2) Error Propagation: a bit error affects decipherment of two blocks.

### Q. What is DES(Data Encryption Standard)?
The Data Encryption Standard is a symmetric-key algorithm for the encryption of digital data.

### Q. How DES works (What are the operation modes it uses?)
It uses 4 modes of operation:

1) ECB: Electronic Code Book
2) CBC: Cipher Block Chaining
3) CFB: Cipher Feedback
4) OFB: Output Feedback

<img src="https://i.ytimg.com/vi/Y61qn_SQl40/maxresdefault.jpg" height="300" width="500" />

### Q. What is AES(Advanced Encryption System)?
The Advanced Encryption Standard (AES) is a symmetric block cipher. It is used because 56 bit key in DES is too short for fast speed computers.

### Q. Selection standards of AES.
Selection based on **security**, **efficiency** and **implementation**.

### Q. Comparison between DES and AES.

|  | DES | AES |
| --- | --- | --- |
| Date | 1976 | 1999 |
| Block size | 64 | 128 |
| Key length | 56 | 128, 192, 256 |
| Encryption primitives | Substitution, permutation | Substitution, shift, bit mixing |
| Cryptographic primitives | Confusion, diffusion | Confusion, diffusion |
| Design | Open | Open |
| Design rationale | Closed | Open |
| Selection process | Secret | Secret, but accept open public comment |
| Source | IBM, enhanced by NSA | Independent Dutch cryptographers |

### Q. Pros and cons of Symmetric Cipher.
Pros: Light computation load; Easy to implement, especially by hardware.

Cons: Key distribution and Scalability.

## 📖 Asymmetric encryption (RSA) <div id="asymmetric"></div>

### Q. What is Asymmetric Cryptosystem?
It uses the **public key** for the encryption, and a **private key** is used for decryption.

### Q. What is RSA Encryption and how it works?
RSA is one of the first public-key cryptosystems and is widely used for secure data transmission. The acronym RSA is the initial letters of the surnames of Ron Rivest, Adi Shamir, and Leonard Adleman, who publicly described the algorithm in 1977.

<img src="https://i.ytimg.com/vi/kKgp0KdpOhQ/maxresdefault.jpg" height="300" width="500" />

### Q. Limitation of RSA encryption.
RSA is only able to encrypt data to a maximum amount equal to your key size (2048 bits = 256 bytes), minus any padding and header data (11 bytes for PKCS#1 v1. 5 padding). As a result, it is often not possible to encrypt files with RSA directly.

It is also not inefficient, the encryption time is long.

### Q. Asymmetric vs. Symmetric.
| Asymmetric | Symmetric |
| --- | --- |
| Key exchange over public channel | Key exchange must be done over secure channel |
| Scalable for multi-party communication | Non-scalable for multi-party communication |
| Long keys (e.g., 1024 bits) | Relative short keys (e.g., 128 bits) |
| Slow implementation. RSA software can encrypt 7.4~21.6 Kb/sec. Fastest RSA hardware can encrypt 1 Mb/sec | Fast implementation. In software, DES is generally 100 times faster than RSA. In hardware, DES is between 1000 to 10,000 times faster |

## 📖 Message Integrity and Authentication <div id="message"></div>

### Q. Does encryption(such as ECB and CBC) provide integrity?
No.

### Q. What is Message Authentication?
It is the cryptographic techniques to protect message integrity (or detect whether a message is modified).

### Q. Properties of Hash function.
1) **One-way**: easy to compute but hard to inverse.
2) **Collision Resistant**: Given H(x), it’s computationally infeasible to find x’ such that: x != x’ but H(x)=H(x’). (x’ exists! But no one can find it out in practice!)
3) **Fixed Length**: Variable-length input gets fixed-length output.

### Q. What are the Standard Hash functions available and their properties?
**MD4, MD5**: Not recommended to use.

**SHA**:  SHA1, SHA2, SHA3.

(Clearly, only a one-character change, i.e., a one bit change (from 80 Hex to 81 Hex) in the input causes a significant change in the pattern of the digest, and it is this resulting transformation that provides the foundation for protecting the integrity of information.)

### Q. What are preimage attack and collision attack?
1) **Preimage attack** (against one-way feature). Given h, find M such that H(M)=h. 2^(|h|) tries (365 tries for a given birthday)
2) **Collision attack** (against collision resistant feature). Given H(), find M’ and M’’ such that H(M’)=H(M’’). 2^(|h|/2) tries (about 20 tries for two same birthdays)

### Q. What is MAC(Message Authentication Code)?
MAC algorithm is a symmetric key cryptographic technique to provide message authentication. For establishing MAC process, the sender and receiver share a symmetric key K.

Limitations: Shared secret; Repudiation.

### Q. What is Non-repudiation?
Non-repudiation is the assurance that someone cannot deny the validity of something. Non-repudiation is a legal concept that is widely used in information security and refers to a service, which provides proof of the origin of data and the integrity of the data.

### Q. What is DES-MAC?
It is a MAC scheme based on the DES cipher.

### Q. What is public key signature?
In a public-key cryptosystem, a public key is a key that can be used for verifying digital signatures generated using a corresponding private key. In some cryptosystems, public keys can also be used for encrypting messages so that they can only be decrypted using the corresponding private key.

### Q. What is RSA signature?
RSA (Rivest–Shamir–Adleman) is one of the first public-key cryptosystems and is widely used for secure data transmission. Its security relies on the **difficulty of factoring large
composite numbers**. The RSA digital signature scheme applies the sender's private key to a message to generate a signature. The signature can then be verified by applying the corresponding public key to the message and the signature through the verification process, providing either a valid or invalid result.

### Q. Compare RSA signature and MAC, DES-MAC.
RSA has Non-repudiation and Public Verification properties.

## 📖 Certificate and PKI <div id="pki"></div>

### Q. What is CA(Certification Authority)?
A Certification Authority (CA) is an entity that issues digital certificates. The digital certificate certifies the ownership of a public key.

### Q. What does a Certificate Request look like?


### Q. What does a Certificate look like (mandatory components)?
### Q. What is Certificate Verification?
### Q. What is Certificate Revocation List (CRL)?
### Q. What is PKI?
### Q. What are the approaches for trust establishment?
### Q. What is the Hierarchy approach?
### Q. What is cross-sign?
### Q. What are the common email threats?

## 📖 User Authentication <div id="user"></div>

### Q. What are the three forms of shared secrets?
### Q. What are three attack scenarios?
### Q. What is Exhaustive Search?
### Q. How to counter online attacks?
### Q. What is Off-line Exhaustive Search?
### Q. What is Dictionary Attack?
### Q. The Art of choosing good password.
### Q. Compare Challenge-Response and Time Stamp.
### Q. What is Lamport Scheme and its limitations?

## 📖 Firewall and IDS <div id="ids"></div>

### Q. What is firewall?
### Q. What are the close policy and open policy?
### Q. What are the three types of firewalls?
### Q. Limitations of firewalls?
### Q. What is IDS?
### Q. What are the properties of an ideal IDS?
### Q. FW vs. IDS
### Q. How to calculate accuracy of IDS?
### Q. How to reduce false positive and false negative?
### Q. Misuse/Signature-based Detection vs. Anomaly-based
### Q. Why do most use the first one?
### Q. What is network-based intrusion detection (NIDS)?
### Q. Problems with NIDS.
### Q. What is HIDS?
### Q. What is a system call?

## 📖 Software Security <div id="software"></div>

### Q. Describe program translating process.
### Q. What is translator?
### Q. Differences between assembler, compiler and interpreter.
### Q. Differences between machine language, assembly language and high-level language.
### Q. What is CISC?
### Q. What is call stack?
### Q. What is stack layout?
### Q. What is buffer overflow?
### Q. What happens if source string is too long?

## 📖 Network Security <div id="networking"></div>

### Q. What are IP Address and MAC Address?
### Q. What is ARP?
### Q. What does ARP table look like?
### Q. How ARP works?
### Q. What is ARP poisoning?
### Q. What is AS Numbers?
### Q. What is BGP?
### Q. What is DoS?
### Q. What is SYN flooding and how to prevent it?


## 📖 Networking <div id="networking"></div>
### Q. What are IP address, Hostname and Domain name?
### Q. What is Router?
### Q. What are components in a Router Architecture?
### Q. What is DNS and How does DNS work?
### Q. How transport service and protocols work? 
### Q. Compare TCP and UDP.
### Q. What is Port Number?
### Q. What is HTTP?

