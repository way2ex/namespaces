---
namespace-identifier: tron-caip2
title: Tron Namespace - Chains
author: Justin Zhu (@way2ex)
discussions-to: []
status: Draft
type: Standard
created: 2024-02-03
updated: 2024-02-03
requires: CAIP-2
---

# CAIP-2

_For context, see the [CAIP-2][] specification._

## Rationale

In CAIP-2 a general blockchain identification scheme is defined. This is the
implementation of CAIP-2 for Tron. Blockchains(also named "[Tron Networks][]") in the "tron" namespace are validated by **the last four bytes** of their genesis block hash; each blockchain is maintained by a one or more nodes, with its own JSON-RPC API service.

## Syntax

The namespace "tron" refers to the Tron open-source blockchain platform.

### Reference Definition

The definition for this namespace will use the `genesisHash` as an identifier
for different Tron chains. The method for calculating the chain ID is as
follows with pseudo-code:

```
"0x" + slice(genesisHashHexString, 64 - 8, 64)
```

### Resolution Method

To resolve a blockchain reference for the Tron namespace, make a JSON-RPC
request to the [RPC Endpoints][] of a blockchain node with method
`eth_chainId`, for example:

```jsonc
// Request
{
  "jsonrpc": "2.0",
  "method": "eth_chainId",
  "params": [],
  "id": 1
}


// Response
{
  "jsonrpc": "2.0",
  "id": 1,
  "result": "0x2b6653dc"
}
```

The response will return **the last four bytes** of their genesis block hash in hex format.

## Test Cases

This is a list of manually composed examples

```
# Tron Mainnet
tron:0x2b6653dc

# Tron Shasta Testnet
tron:0x94a9059e

# Tron Nile Testnet
tron:0xcd8690dc

```

## References

- [RPC Endpoints][] - RPC reference in Tron official documentation

[CAIP-2]: https://github.com/ChainAgnostic/CAIPs/blob/master/CAIPs/caip-2.md
[Tron Networks]: https://developers.tron.network/docs/networks
[RPC Endpoints]: https://developers.tron.network/reference/json-rpc-api-overview

## Copyright

Copyright and related rights waived via [CC0](https://creativecommons.org/publicdomain/zero/1.0/).
