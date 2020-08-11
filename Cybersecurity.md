[Introduction](#introduction)

[Encryption Basics](#encryption)

[From DES to AES](#des)

[RSA](#rsa)

[Message Integrity and Message Authentication](#message)

[Certificate and PKI](#pki)

[User Authenticatoin](#user)

[Firewall and IDS](#ids)

[Software Security](#software)

[Networking](#networking)

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


### Q. What is Substitution Cipher and its weakness?
### Q. Features of (why it is secure and its limitations) One-Time Pad.
### Q. What is permutation and its weakness?
### Q. What are confusion and diffusion?
### Q. What is product cipher?
### Q. Shannon’s characteristics of good ciphers.
### Q. Properties of “Trustworthy” encryption systems.
### Q. What are computational security and unconditional security?


## 📖 From DES(Data Encryption Standard) to AES (Advanced Encryption Standard) <div id="des"></div>

### Q. What is Block Cipher?
### Q. What is initialization vector?
### Q. Main properties of ECB and CBC.
### Q. What is DES?
### Q. How DES works (What are the operation modes it uses?)
### Q. What is AES?
### Q. Selection standards of AES.
### Q. Comparison between DES and AES.
### Q. Pros and cons of Symmetric Cipher.
### Q. CFB properties.

## 📖 RSA (Rivest–Shamir–Adleman) <div id="rsa"></div>

### Q. What is Asymmetric Cryptosystem?
### Q. Limitation of RSA encryption.
### Q. Asymmetric vs. Symmetric.
### Q. What is Envelope Encryption?

## 📖 Message Integrity and Message Authentication <div id="message"></div>

### Q. What is Message Authentication?
### Q. Properties of Hash function.
### Q. What are the Standard Hash functions available and their properties?
### Q. What are preimage attack and collision attack?
### Q. What is MAC?
### Q. What is HMAC?
### Q. What is DES-MAC?
### Q. What is Repudiation?
### Q. What is public key signature?
### Q. What is RSA signature?
### Q. Compare RSA signature and RSA encryption.
### Q. Compare RSA signature and MAC, DES-MAC.

## 📖 Certificate and PKI <div id="pki"></div>

### Q. What is CA?
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

