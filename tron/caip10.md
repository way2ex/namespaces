---
namespace-identifier: tron-caip10
title: Tron Namespace - Addresses
author: Justin Zhu (@way2ex)
discussions-to: https://github.com/ChainAgnostic/namespaces/pull/26
status: Draft
type: Standard
created: 2024-02-03
updated: 2024-02-03
requires: ["CAIP-2", "CAIP-10"]
---

# CAIP-10

_For context, see the [CAIP-10][] specification._

## Rationale

Tron "addresses" has two format: Hex and Base58. The Hex format is the last 20 bytes of the Keccak-256 result of the PublicKey in the elliptic curve digital signature algorithm ECDSA-secp256k1 and add the character "41" as leading. The address in Base58 format can be obtained from the base check calculation of a Hex address.

## Syntax

The syntax of a Tron address matches the following regular expression:

`T[1-9A-HJ-NP-Za-km-z]{33}|41[0-9A-F]{40}`

## Chain IDs

_For context, see the [CAIP-2][] specification._

| Network Name   | Chain ID   |
| -------------- | ---------- |
| Mainnet        | 0x2b6653dc |
| Shasta Testnet | 0x94a9059e |
| Nile Testnet   | 0xcd8690dc |

## Test Cases

```
# Tron Mainnet
tron:0x2b6653dc:TDpBe64DqirkKWj6HWuR1pWgmnhw2wDacE

# Tron Shasta Testnet
tron:0x94a9059e:TU6JdEDQGPus64LTMksvnxF2cv4FQrXPCa

# Tron Nile Testnet
tron:0xcd8690dc:TNPeeaaFB7K9cmo4uQpcU32zGK8G1NYqeL
```

## References

[Tron Account](https://developers.tron.network/docs/account)
[CAIP-2]: https://github.com/ChainAgnostic/CAIPs/blob/master/CAIPs/caip-2.md
[CAIP-10]: https://github.com/ChainAgnostic/CAIPs/blob/master/CAIPs/caip-10.md

## Rights

Copyright and related rights waived via [CC0](https://creativecommons.org/publicdomain/zero/1.0/).
