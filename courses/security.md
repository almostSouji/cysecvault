---
id: security
aliases: []
tags:
  - lecture
---

# L2 Symmetric Cryptography
## Goals

- Explain [[1794338611-VZLD|confidentiality]] and [[1794338619-NVKG|integrity]] and why they need different mechanisms
- Explain why the [[1794338639-GREY|one-time-pad]] is perfectly secret and why reusing or shortening its key breaks it
- Describe what a [[1794338659-JCUR|block cipher]] does and the structure of [[1794338667-WNRF|AES]] at a high level.
- Explain why [[1794338687-UKSX|ECB]] leaks patterns, how [[1794338695-RYJR|CBC]] and [[1794338698-WEJY|CTR]] avoid this, and what they do not protect against
- Build integrity with [[1794338716-CSFF|MAC]]s [[1794338724-GVYX|HMAC]] and explain why $H(k||m)$ is not a secure MAC.
- Choose [[1794338765-NLNA|Authenticated Encryption]] when you need [[1794338611-VZLD|confidentiality]] and [[1794338619-NVKG|integrity]]
- Explain why security depends on unpredictable randomness, and true vs. pseudorandomness

## Takeaways

- [[1794338611-VZLD|confidentiality]] and [[1794338619-NVKG|integrity]] are different goals that need different mechanisms
- [[1794338639-GREY|one-time-pad]] is perfectly secret, but only if hte key is random, as long as the message, and never reused
- [[1794338659-JCUR|block cipher]]s [[1794338667-WNRF|AES]] encrypt single blocks; modes of operation handle longer messages.
- Never use [[1794338687-UKSX|ECB]]; [[1794338695-RYJR|CBC]] and [[1794338698-WEJY|CTR]] hide patterns but provide no [[1794338619-NVKG|integrity]].
- Never reuse a nonce in [[1794338698-WEJY|CTR]] or [[1794338938-HPHI|GCM]]
- [[1794338716-CSFF|MAC]]s provide [[1794338619-NVKG|integrity]]: use [[1794338724-GVYX|HMAC]] not $H(k||m)$
- In practice, use [[1794338765-NLNA|Authenticated Encryption]] ([[1794338995-GLFU|AES-GCM]], [[1794339009-LFIU|ChaCha20-Poly1305]])

# L3 Asymmetric Cryptography
## Goals

- Explain the [[1794339067-LZYD|key distribution problem]] and how [[1794339075-FKVW|Diffie-Hellman]] solves it.
- Explain why unauthenticated [[1794339075-FKVW|Diffie-Hellman]] is vulnerable to a [[1794339096-XWLX|machine-in-themiddle]] attack.
- Compute small examples with modular arithmetic, and run [[1794339113-DKUQ|RSA]] key generation, encryption, and decryption by hand.
- Explain why textbook [[1794339113-DKUQ|RSA]] is insecure and why padding is needed.
- Explain why [[1794339151-IOJI|asymmetric cryptography]] is slow and how [[1794339171-BVNG|hybrid encryption]] combines both worlds
- Explain [[1794339182-GPFW|digital signatures]], [[1794339189-FPEW|non-repudiation]], and why we sign $H(m)$ instead of $m$

## Takeaways

- [[1794339075-FKVW|Diffie-Hellman]] derives a shared key from public values, but needs [[1794339250-CBXO|authentication]] against [[1794339096-XWLX|machine-in-themiddle]] attacks.
- [[1794339151-IOJI|Asymmetric cryptograpy]]: publish pk, keep sk; [[1794339113-DKUQ|RSA]] rests on hardness of factoring.
- Never use textbook [[1794339113-DKUQ|RSA]]: padding is essential ([[1794339327-WOOL|OAEP]], [[1794339331-OVPF|PSS]])
- [[1794339151-IOJI|Asymmetric cryptograpy]] is slow: use [[1794339171-BVNG|hybrid encryption]] in practice.
- [[1794339182-GPFW|Digital signatures]] give [[1794338619-NVKG|integrity]] and [[1794339189-FPEW|non-repudiation]]; sign H(m) not m
- Quantum computers threaten [[1794339113-DKUQ|RSA]], [[1794339075-FKVW|Diffie-Hellman]], and [[1794339402-ZIXW|ECC]]; post quantum schemes are being deployed.
- [[1794339421-BHEZ|Cryptograhy]] mostly works: most vulnerabilites are in protocols and implementations (L4ff)

# L4 Cryptographic Protocols
# L5 TLS
# L6 Certificates
# L7 Bitcoin


