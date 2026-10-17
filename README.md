# SockLove Docs

[![Release](https://img.shields.io/badge/release-1.0%20%C2%B7%20Proposal-FF3355?style=flat-square)](https://github.com/socklove-eth/.github/blob/v1.0/RELEASE.md)
[![Licence](https://img.shields.io/badge/licence-CC%20BY%204.0-666?style=flat-square)](https://github.com/socklove-eth/docs/blob/v1.0/LICENSE)

> What exists, and what is promised. Nothing more.

---

## 🗺️ Map

| Document | Read it for |
|---|---|
| [ARCHITECTURE.md](https://github.com/socklove-eth/docs/blob/v1.0/ARCHITECTURE.md) | How the 📄 **[Pages](https://github.com/socklove-eth/pages/tree/v1.0)** work. |
| [LEXICON.md](https://github.com/socklove-eth/docs/blob/v1.0/LEXICON.md) | What a word means. |
| [STYLE.md](https://github.com/socklove-eth/docs/blob/v1.0/STYLE.md) | The 🖋️ **[Ink](https://github.com/socklove-eth/docs/blob/v1.0/STYLE.md)** and the ✨ **[Light](https://github.com/socklove-eth/docs/blob/v1.0/STYLE.md)**: how 🧦💜 **[SockLove](https://github.com/socklove-eth)** reads and looks. |
| [RELEASES.md](https://github.com/socklove-eth/docs/blob/v1.0/RELEASES.md) | Making and verifying a release; `1.0` and what is promised. |
| [REGISTRY.md](https://github.com/socklove-eth/docs/blob/v1.0/REGISTRY.md) | The 🔧 **[Living Registry](https://github.com/socklove-eth/docs/blob/v1.0/REGISTRY.md)**. |
| [PHILOSOPHY.md](https://github.com/socklove-eth/docs/blob/v1.0/PHILOSOPHY.md) | Why. **The only document not scoped to a release.** |

---

## 🔏 Seal

[PHILOSOPHY.md](https://github.com/socklove-eth/docs/blob/v1.0/PHILOSOPHY.md)
is sealed by the 💍 **[Ring](https://etherscan.io/address/socklove.eth)**:

- **[SHA-256](https://csrc.nist.gov/pubs/fips/180-4/upd1/final):**
`f1940c694e4f072e99ca264a8f5217d001512371b8beeecd059071916db15bac`.
- **Transaction:**
`0xeb5020bdddd4ad88f565751054a9c1c2b2eb9f4dfb7666d29c201e62629a3e14`.

Check it with
[sha256sum](https://www.gnu.org/software/coreutils/manual/html_node/sha2-utilities.html)
and [cast](https://www.getfoundry.sh/cast); `0x1626ba7e` means sealed:

```bash
sha256sum PHILOSOPHY.md
cast call 0x0857293192bF97Ee73bB471c185E1933Fa51E0ca \
  'isValidSignature(bytes32,bytes)(bytes4)' 0x<HASH> 0x --rpc-url <RPC_URL>
```

---

## ⚖️ Licences

[CC BY 4.0](https://creativecommons.org/licenses/by/4.0/); the name, logo,
favicon and
🖼️ **[Plate](https://github.com/socklove-eth/.github/blob/v1.0/profile/assets/plate.jpg)**
are reserved:
[TRADEMARKS.md](https://github.com/socklove-eth/.github/blob/v1.0/TRADEMARKS.md).
