# SockLove Docs Registry

> The settings live on the name; only the ring writes them.

---

## 🔧 Living Registry

The 🔧 **Living Registry** is
🧦💜 **[SockLove](https://github.com/socklove-eth)**'s mutable configuration:
📛 **[ENS](https://ens.domains/)** text records
([ENSIP-5](https://docs.ens.domains/ensip/5)) on 🌐 `socklove.eth`, at its
pinned resolver, written without a release by the
💍 **[Ring](https://etherscan.io/address/socklove.eth)** alone, which owns the
name.

- **Read** a record in any ENS app, or with
[cast](https://www.getfoundry.sh/cast):
  ```bash
  cast call 0xF29100983E058B709F3D539b0c765937B804AC15 \
    'text(bytes32,string)(string)' "$(cast namehash socklove.eth)" rpc.endpoints \
    --rpc-url <RPC_URL>
  ```
- **Change** one with a 🔐 **[Safe](https://safe.global/)** transaction,
`setText(node, key, value)` on the resolver; an empty value removes it.

---

## 📇 Records

| Key | Read by | Value |
|---|---|---|
| `rpc.endpoints` | 💒 **[Altar](https://altar.socklove.eth.limo)** | [RPC](https://ethereum.org/developers/docs/apis/json-rpc/) endpoints, comma-separated, that Altar tries ahead of its baked set. |

Altar keeps, in order, the https endpoints on public hosts, without credentials,
whatever chain each claims; a host is judged by its name or address as the
[URL parser](https://url.spec.whatwg.org/) reads it. An entry must already be in
the form the URL parser writes — lowercase host, no default port — though a
bare host may leave off its trailing slash, and spaces around commas are
allowed. Anything else, and any repeat, is dropped, never repaired. How Altar
reads it:
[ARCHITECTURE.md](https://github.com/socklove-eth/docs/blob/v1.0/ARCHITECTURE.md).
