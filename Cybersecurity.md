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

### Q. What are included in a Certificate?
1) Date of issue
2) Validity date
3) Signature Algorithm
4) Issuer
5) Subject
6) Subject public key info
7) CA’s signature

### Q. Describe Certificate Verification process?
1) obtain one's certificate, either by receiving it from holder or retrieving it from some directory.
2) Check whether it has expired or not. Lastly, we verify the signature using CA's public key.
3) Verify the entire certification chain.
4) Check whether the certificate is in the CRL.

### Q. What is Certificate Revocation List (CRL)?
A CRL is a list of digital certificates that have been revoked by the issuing Certificate Authority (CA) before their scheduled expiration date and should no longer be trusted.

### Q. What is PKI?
PKI stands for Public Key Infrastructure. It is a set of policies, procedures, and products; used to implement public key cryptosystem in a large setting. 

### Q. What are the approaches for trust establishment?
A hierarchical approach or A peer to peer approach.

### Q. What is the Hierarchy approach?
In hierarchy appraoch, high-level CA sign low-level CA’s public key. Root CA issues its own certificate and is JUST trusted by all users. It’s own certificate is signed by its own private key.

It is harder for Mallory to impersonate a high-level CA since a high level CA is widely exposed to public

### Q. What is cross-sign?
Two root CA sign each other’s certificate.

### Q. What are the common email threats?
1) Message eavesdropping
2) Content modification
3) Origin modification
4) Content/origin forgery by outsider/recipient

## 📖 User Authentication <div id="user"></div>

### Q. What are three attack scenarios?
1) Attack at client side. Eg. Key logger and malware
2) Attack in communication channel. Eg. Eavesdropping
3) Attack at server side. Eg. Access to password file

### Q. What is Exhaustive Search?
Adversary tries all possible passwords on-line or off-line.

### Q. How to counter online attacks?
1) Choosing long password 
2) Limiting the number of tries 
3) Slowing down log-in process

### Q. What is Off-line Exhaustive Search?
Adversary (with the help of some automatic tool) obtains the encrypted password file and tries every possible password and encrypt it, after that the adversary compares the ciphertext of each tried password to all passwords in the password file.

### Q. What is Dictionary Attack?
Adversary (with the help of some automatic tool) creates a dictionary of commonly used passwords (probably including all the words in a common dictionary) and pre-computes password file of the dictionary. After that the adversay looks for a match between the pre-computed password file and the real password file. Dictionary attacks are fast, but only work for weak passwords.

### Q. The Art of choosing good password.
1) DO NOT use your boyfriend/ girlfriend/ parents/ siblings/ pet’s **name** as your password.
2) DO NOT use words found in the **dictionary** as your password.
3) DO NOT use your or anybody mentioned in Point 1’s **birth date** as your password.
4) DO try and use a **combination of alphabets, digits and special characters.  Both lower and upper case** should be used. Such a password is one of the most difficult to break passwords.

## 📖 Firewall and IDS <div id="ids"></div>

### Q. What is firewall?
A firewall is a network security system that **monitors and controls** incoming and outgoing network traffic based on predetermined **security rules**. A firewall typically establishes a barrier between a trusted internal network and untrusted external network.

### Q. What are the close policy and open policy?
Close policy: Default deny with white list.

Open policy: Default permit with black list.

### Q. What are the three types of firewalls?
IP layer: Packet filtering gateway (screening router)

TCP layer: Circuit relay, stateful inspection

Application layer: Application proxy gateway

### Q. Limitations of firewalls?
Single Point of Failure; Performance bottleneck

### Q. What is IDS?
An intrusion detection system is a device or software application that monitors for malicious activity or policy violations within a network. Any malicious activity or violation is typically reported or collected centrally using a security information and event management system.

### Q. What are the properties of an ideal IDS?
1) 100% accuracy
2) In real time manner
3) Complete diagnosis
4) Effective recommendations on how to react

### Q. FW vs. IDS
Firewall enforces **policies** on controlling packets in the gateways to block unauthorized access, while IDS analyses **whole packets** to detect intrusions and report them within the network in real time.

### Q. How to calculate accuracy of IDS?
**False positive (alarm) rate**: number of false-alert / total number of alerts

**False negative (miss) rate**: number of missed-attacks / total number of non-alerts

### Q. How to reduce false positive and false negative?
Reduce false positive: reduce the sensitivity of IDS

Reduce false negative: increase the sensitivity of IDS

### Q. Misuse/Signature-based Detection vs. Anomaly-based
**Misuse/signature-based**:
1) Remembers “signatures” of “bad things”
2) Not matching = “good”
3) Good detection rate but cannot detect zero-day exploits

**Anomaly-based**:
1) Remembers characterization of “good things”
2) Not matching = bad
3) Can detect attacks that have not been observed before but has high false-alarm rate.

### Q. Why do most use the first one?
1) The second one has too high false alarms.
2) The second one depends on the contexts.
3) Users often are not aware that they have zero-day attacks.

### Q. What is network-based intrusion detection (NIDS)?
A network-based intrusion detection system detects malicious traffic on a network. NIDS usually require promiscuous network access in order to analyze all traffic, including all unicast traffic. NIDS are passive devices that do not interfere with the traffic they monitor. Fig. 7.2 shows a typical NIDS architecture. The NIDS sniffs the internal interface of the firewall in read-only mode and sends alerts to a NIDS Management server via a different (ie, read/write) network interface.

<img src="https://ars.els-cdn.com/content/image/3-s2.0-B9780128112489000073-f07-02-9780128112489.jpg?_" height="280" width="450" />

Advantage of passive monitoring:
1) Unobtrusive
2) Difficult to evade if done at low level of network operation

### Q. What is HIDS?
A host-based intrusion detection system (HIDS) monitors and analyzes system configuration and application activity for devices running on the enterprise network. The HIDS sensors can be installed on any device, regardless of whether it’s a desktop PC or a server.

HIDS sensors essentially take a snapshot of existing system files and compare them with previous snapshots. They look for unexpected changes, such as overwriting, deletion and access to certain ports. Consequently, alerts are sent to administrators to investigate activities that seem iffy.

### Q. NIDS vs. HIDS
Each of these intrusion detection systems come with their own strengths. NIDS works in real-time, which means it tracks live data and flags issues as they happen. On the other hand, HIDS examines historical data to catch savvy hackers that use non-conventional methods that might be difficult to detect in real-time.

The ideal scenario is to incorporate both HIDS and NIDS since they complement each other. NIDS offers faster response time while HIDS can identify malicious data packets that originate from inside the enterprise network.

### Q. What is a system call?
A system call is the programmatic way in which a computer program requests a service from the **kernel** of the operating system.

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
ARP stands for Address Resolution Protocol. It is a communication protocol used for discovering the link layer address, such as a MAC address, associated with a given internet layer address, typically an IPv4 address.

### Q. What does ARP table look like?

### Q. How ARP works?

### Q. What is ARP poisoning?

### Q. What is AS Numbers?


### Q. What is BGP?
BGP is short for Border Gateway Protocol and it is the routing protocol used to route traffic across the internet.

### Q. What is DoS?
DoS stands for Denial of Service. It is a cyber-attack in which it overwhelms the victim to the point of unresponsiveness to legitimate users.

### Q. What is DDoS?
DDoS stands for distributed denial-of-service. It is a kind of DoS attack. The incoming traffic flooding the victim originates from many different sources. This effectively makes it impossible to stop the attack simply by blocking a single source.

### Q. What is SYN flooding and how to prevent it?
A SYN(Synchronize) flood is a form of **denial-of-service attack** in which an attacker sends a succession of SYN requests to a target's system in an attempt to consume enough server resources to make the system unresponsive to legitimate traffic.


## 📖 Networking <div id="networking"></div>
### Q. What are IP address, Hostname and Domain name?
### Q. What is Router?
### Q. What are components in a Router Architecture?
### Q. What is DNS and How does DNS work?
### Q. How transport service and protocols work? 
### Q. Compare TCP and UDP.
### Q. What is Port Number?
### Q. What is HTTP?

