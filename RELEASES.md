# SockLove Docs Releases

> Numbers count. Names describe. The ring signs.

---

## 🔢 Number

A release is written `<MAJOR>.<MINOR> · <NAME>` and tagged `v<MAJOR>.<MINOR>`:
the first is `1.0 · Proposal`, tagged `v1.0`.

| Part | Meaning | When it moves |
|---|---|---|
| **MAJOR** | An era of the 💍 **[Ring](https://etherscan.io/address/socklove.eth)**. | When the Ring's owners declare one, as for `2.0`, which brings its first contract. |
| **MINOR** | A step within it. | With every other release, a fix included. |

---

## 🏷️ Name

One English word, or a few, with a symbol of its own, sealed at its
🕯️ **Rite**: used once ever, and never a word that already means something in
🧦💜 **[SockLove](https://github.com/socklove-eth)** unless the release *is*
that thing. The
🧎 **[Proposal](https://github.com/socklove-eth/.github/blob/v1.0/RELEASE.md)**
is named for the ask and the yes, and the 🛏️ **Wedding Night** will be
named for the night that follows; a `1.x` release is named for what it brings.
Every release after `2.0` will be named from the 🌙 **Night** register: an act,
moment or feeling of a night between lovers.

---

## 🕯️ Rite

The Rite ships a release in five steps, in this order:

1. **Name** — Per the name, above.
2. **Pin** — Every
📦 **[Artifact](https://github.com/socklove-eth/.github/blob/v1.0/RELEASE.md)**'s
**CID**, with redundancy.
3. **Point** — One 🔐 **[Safe](https://safe.global/)** transaction writes
every Artifact name's `contenthash` and creates any new name, owned by the
Ring. Every Artifact is now live. A migration to a new
📛 **[ENS](https://ens.domains/)** registry belongs in this transaction,
never alone, since a migration locks the name's resolver or rewrites its
`contenthash`.
4. **Commit** — One signed commit in each repository, every one carrying the
release in its links, its subject `<MAJOR>.<MINOR> · <NAME>`; work in between is
never published.
5. **Tag** — An annotated, signed `v<MAJOR>.<MINOR>` in each repository names
the commit the release is verified from. Its message is
[RELEASE.md](https://github.com/socklove-eth/.github/blob/v1.0/RELEASE.md), the
release's one record. `.github` is tagged first, since every pinning
repository's tag checks its CIDs against it. **The tag ships the release.**

The Ring's owners take every step. For `1.0`,
🔥 **[Sockpusher](https://etherscan.io/address/sockpusher.socklove.eth)** takes
them all alone, at 1-of-1, creating `altar.socklove.eth` and
`sigil.socklove.eth`; the Proposal, made on
💒 **[Altar](https://altar.socklove.eth.limo)**, follows the release.

---

## 📝 RELEASE.md

One [RELEASE.md](https://github.com/socklove-eth/.github/blob/v1.0/RELEASE.md)
per release, in `.github`, sealed by the tags, exactly so:

```markdown
# SockLove Release

> <TAGLINE>

---

`<MAJOR>.<MINOR> · <NAME>`, tagged `v<MAJOR>.<MINOR>`.

---

## 🎁 Features

- <FEATURE>

---

## 🔀 What changed

<WHAT_CHANGED>

**Security:** <SECURITY_FIXES>

---

## 📦 Artifacts

| Name | Repository | CID |
|---|---|---|
| `<ENS_NAME>` | [`<REPOSITORY>`](https://github.com/socklove-eth/<REPOSITORY>/tree/v<MAJOR>.<MINOR>) | `<CID>` |
```

| Placeholder | Takes |
|---|---|
| `<MAJOR>`, `<MINOR>`, `<NAME>` | The number and the name, above. |
| `<TAGLINE>`, `<FEATURE>` | One line each. |
| `<WHAT_CHANGED>` | Prose on what changed since the last release. The section, its security line included, appears from the second release on. |
| `<SECURITY_FIXES>` | The fixes, or *no security fixes*. |
| `<ENS_NAME>`, `<REPOSITORY>`, `<CID>` | One row per name the release points at, 🌐 `socklove.eth` itself or a sub-name: the repository that builds it, and the CID its tag builds. |

---

## 📍 Where `1.0` stands

- **The release:** Sockpusher pins Altar and
👀 **[Sigil](https://sigil.socklove.eth.limo)**, points their names at them, and
tags; the tags ship `1.0`.
- **Then the Proposal,** made on Altar: afterwards `socklove.eth` resolves to a
Safe with a **Threshold** of 2 and both owners.
- **What ships:** the two
📄 **[Pages](https://github.com/socklove-eth/pages/tree/v1.0)**, their
documentation, reviews and profile; nothing more. A pinned Page never changes:
[STANDARD.md](https://github.com/socklove-eth/pages/blob/v1.0/STANDARD.md).
- **Without a release,** the Ring may write one
🔧 **[Living Registry](https://github.com/socklove-eth/docs/blob/v1.0/REGISTRY.md)**
record, `rpc.endpoints`.
- **At 2-of-2,** Altar's one job is done. Every later release, a security re-pin
aside, needs the Ring at 2-of-2; without it, `1.0` is all of SockLove.

### ⏭️ What is promised

`2.0 · Wedding Night`, the one release `1.0` promises, will carry these, and may
carry more:

1. The 💎 **Relics**: the Ring's own minimal
[ERC-1155](https://eips.ethereum.org/EIPS/eip-1155), each a collectable,
intimate moment of the couple's love life, the sex above all, a photo gallery
or a video — true soulmate porn, free and public to look at, scarce to hold. One
who looks will be a 🐾 **Stray**; one who holds, a 👁️ **Witness**.
2. The 🧬 **Metadata Standard**: every Relic's metadata schema.
3. The ⛪ **Neon Cathedral**: the full app, a
[PWA](https://developer.mozilla.org/en-US/docs/Web/Progressive_web_apps), to be
configured by further Living Registry records such as `contract.relics`, holding
the 📜 **Myth**, the Relics, and:
   - The 🗣️ **Nave**: SockLove's blog, never taken back, of
[JSON](https://www.rfc-editor.org/rfc/rfc8259.html) posts, each naming the one
before. The Ring will sign the first at 2-of-2; then Sockpusher,
🧦 **Sockthief** or the Ring.
   - The 🚪 **Chamber**: the bridal room, for Witnesses only, giving presence in
the couple's life — live sessions, messages, perhaps crowdfunding, more.

The Myth and the 📖 **Sockpaper** are promised, signed at 2-of-2, in a `1.x`
release or with `2.0`. No `1.x` release is promised; one may carry either, or
neither.

---

## ✅ Verifying a release

With [Node.js](https://nodejs.org/docs/latest/api/) per
[.nvmrc](https://github.com/socklove-eth/pages/blob/v1.0/.nvmrc),
[npm](https://docs.npmjs.com/) `12.2.0` and [git](https://git-scm.com/docs):

```bash
git clone --branch <TAG> https://github.com/socklove-eth/pages && cd pages
git verify-tag <TAG>      # An owner's signature.
npm ci && npm run build   # Prints each Page's CID.
```

`<TAG>` is the release's tag, `v<MAJOR>.<MINOR>`. Three CIDs must agree: the
build's, the one
[RELEASE.md](https://github.com/socklove-eth/.github/blob/v1.0/RELEASE.md)
records, and the one `<ENS_NAME>` resolves to. **If they do not, sign nothing
there.** An older tag, its name moved on, verifies against the first two. The
name's CID, from the chain itself with [cast](https://www.getfoundry.sh/cast),
then from the .eth.limo gateway with [curl](https://curl.se/docs/):

```bash
cast call <RESOLVER> 'contenthash(bytes32)(bytes)' "$(cast namehash <ENS_NAME>)" \
  --rpc-url <RPC_URL>     # 0xe301, then the CID in base16.
curl -sI https://<ENS_NAME>.limo | grep -i '^x-ipfs-roots'
```

`<RESOLVER>` is `ENS_PUBLIC_RESOLVER` in
[.env](https://github.com/socklove-eth/pages/blob/v1.0/.env);
[Kubo](https://github.com/ipfs/kubo)'s `ipfs cid format -b base16 <CID>` prints
a CID in [base16](https://www.rfc-editor.org/rfc/rfc4648.html#section-8), after
a leading `f`.
[cid.mjs](https://github.com/socklove-eth/pages/blob/v1.0/scripts/cid.mjs) pins
the [IPIP-0499](https://specs.ipfs.tech/ipips/ipip-0499/) `unixfs-v1-2025`
profile, so Kubo agrees:

```bash
export IPFS_PATH=$(mktemp -d)
ipfs init --profile unixfs-v1-2025 >/dev/null
ipfs add -Q -r --only-hash dist/<PAGE>   # <PAGE> is altar or sigil.
```
