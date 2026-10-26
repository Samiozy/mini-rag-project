# Cybersecurity Study Notes: Identity And Zero Trust

# Authentication and Access Control
Authentication verifies who a user is, while authorization determines what that user is allowed to do. Multi-factor authentication (MFA) strengthens login by combining something you know (a password), something you have (a hardware token or phone), and something you are (a biometric). The principle of least privilege grants each user only the access strictly needed for their job. Role-based access control (RBAC) assigns permissions to roles rather than individuals, which simplifies administration at scale.

# Zero Trust Architecture
Zero trust abandons the old assumption that everything inside the network perimeter can be trusted. Its guiding motto is "never trust, always verify." Every request is authenticated, authorized, and encrypted regardless of whether it originates inside or outside the network. Micro-segmentation limits an attacker's lateral movement, and continuous verification repeatedly re-evaluates trust based on device posture, user behavior, and context throughout a session rather than only at login.

## Additional study notes (AI-assisted draft; review before submission)
Authentication answers the question of who or what is requesting access, while authorization answers which resources and operations that identity may use. A successful login does not imply unrestricted permissions. Multi-factor authentication reduces dependence on a single secret, though its effectiveness depends on the factors and the attack scenario. An administrator should periodically review role assignments and remove access that is no longer justified.

Zero trust is a design approach rather than a specific product. A network's internal location should not itself count as proof that a request is safe. Policy decisions can incorporate user identity, device condition, requested resource, and current risk. Micro-segmentation makes lateral movement more difficult by requiring explicit access between narrowly defined segments. Continuous verification means trust is reassessed as context changes instead of being granted indefinitely after initial authentication.
