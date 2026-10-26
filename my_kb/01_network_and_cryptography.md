# Cybersecurity Study Notes: Network And Cryptography

# Network Security Fundamentals
Network security protects data as it moves across an organization's infrastructure. Core controls include firewalls that filter traffic according to rules, network segmentation that isolates sensitive systems into separate zones, and virtual private networks (VPNs) that encrypt remote connections over untrusted networks. The defense-in-depth principle layers multiple independent controls so that the failure of any single mechanism does not compromise the entire network.

# Cryptography and Encryption
Cryptography secures information by transforming readable plaintext into unreadable ciphertext. Symmetric encryption such as AES uses one shared secret key for both encryption and decryption and is fast enough for bulk data. Asymmetric encryption such as RSA uses a public/private key pair, which enables secure key exchange and digital signatures. Hash functions like SHA-256 produce fixed-length fingerprints used to verify integrity; unlike encryption, hashing is one-way and cannot be reversed.

## Additional study notes (AI-assisted draft; review before submission)
A firewall makes allow-or-deny decisions using defined network traffic rules. Segmentation can reduce an incident's blast radius because different workloads do not all share the same unrestricted network path. A VPN protects traffic in transit across untrusted networks, but a VPN connection alone does not mean that the user's device or credentials are trustworthy. These controls complement rather than replace each other.

Encryption protects confidentiality when an authorized party has the key needed to decrypt the ciphertext. The management and storage of cryptographic keys matter as much as choosing an encryption algorithm; exposed keys can undermine otherwise strong encryption. Hashing serves a different purpose: it produces a digest useful for integrity checks, but a hash is not a substitute for encryption when confidentiality is required. Digital signatures combine cryptographic operations with identity verification to support integrity and authenticity.
