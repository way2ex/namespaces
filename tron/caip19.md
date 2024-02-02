---
namespace-identifier: tron-caip19
title: Tron Namespace - Asset
author: Justin Zhu (@way2ex)
discussions-to:
status: Draft
type: Standard
created: 2024-02-03
updated: 2024-02-03
requires: ["CAIP-2", "CAIP-10", "CAIP-19", "CAIP-30"]
---

# CAIP-19

_For context, see the [CAIP-19][] specification._

## Rationale

In the Tron ecosystem, there are three kind of assets:

- [TRC-10][] tokens which are issued according to [TRC-10][] standard in TRON Ecosystem.
- [TRC-20][] tokens: issued according to [TRC-20][] starndard contract and referenced
  by its contract address.
- [TRC-721][] tokens: issued according to [TRC-721][] starndard contract and referenced by its contract address, often called an "NFT".

## Syntax

After the [CAIP-2][] (namespace+chainID), a slash defines an `asset_namespace` and an
`asset_reference`. `asset_namespace` MUST refer to an asset type defined by an
[Tron Improvement Proposal][TIP] of category TRC and status Final; the
syntax is simply `trc` prepended to the final TIP number of the published
document defining it, without a hyphen.

- In the case of TRC10 tokens, the namespace is `trc10` and the tokenID is the reference.
- In the case of TRC20 tokens, the namespace is `trc20` and the address of the
  smart contract is the reference.
- In the case of TRC721 tokens, the namespace is `trc721` and the address of the
  smart contract is the reference, with an optional additional identifier for
  the specific token separated from the reference by a "/".

## RegEx

The RegEx validation strings are as follows:

```
asset_id: asset_type + "/" token_id
asset_type: chain_id + "/" + asset_namespace + ":" + asset_reference
chain_id: namespace + Blockchain ID as defined in [CAIP-2](./caip2.md)

asset_namespace: trc[a-z0-9]{2,5}
asset_reference: 0x[a-fA-F0-9]{40}
token_id: [\d]{1,78}
```

## Examples

```
# USDT Token in Mainnet
tron:0x2b6653dc/trc20:TR7NHqjeKQxGTCi8q8ZY4pL8otSzgjLj6t

# HTX Token in Mainnet
tron:0x2b6653dc/trc20:TUPM7K8REVzD2UdV4R5fe5M8XbnR2DdoJ6

# Devikins NFT
tron:0x2b6653dc/trc721:THjYwnDDN6aYxrzKb88CSMTEYjBuHpoYxS

# Devikins NFT ID
tron:0x2b6653dc/trc721:THjYwnDDN6aYxrzKb88CSMTEYjBuHpoYxS/322926
```

## Links

[Tron Account](https://developers.tron.network/docs/account)
[TRC-10]: https://developers.tron.network/docs/trc10
[TRC-20]: https://developers.tron.network/docs/trc20-protocol-interface
[TRC-721]: https://developers.tron.network/docs/trc-721
[CAIP-2]: https://github.com/ChainAgnostic/CAIPs/blob/master/CAIPs/caip-2.md
[CAIP-10]: https://github.com/ChainAgnostic/CAIPs/blob/master/CAIPs/caip-10.md
[CAIP-19]: https://github.com/ChainAgnostic/CAIPs/blob/master/CAIPs/caip-19.md
[CAIP-30]: https://github.com/ChainAgnostic/CAIPs/blob/master/CAIPs/caip-30.md
[TIP]: https://github.com/tronprotocol/tips/tree/master?tab=readme-ov-file#tips

## Copyright

Copyright and related rights waived via [CC0](https://creativecommons.org/publicdomain/zero/1.0/).
