# SockLove Docs Architecture

> Two pages light the way. The ring keeps the vow.

---

## 🏗️ Whole system

🌐 `socklove.eth` resolves to the
💍 **[Ring](https://etherscan.io/address/socklove.eth)**, the
🔐 **[Safe](https://safe.global/)** `1.4.1` at
`0x0857293192bF97Ee73bB471c185E1933Fa51E0ca`. Two
📄 **[Pages](https://github.com/socklove-eth/pages/tree/v1.0)** serve it:
💒 **[Altar](https://altar.socklove.eth.limo)** reads it and asks a wallet to
sign; 👀 **[Sigil](https://sigil.socklove.eth.limo)** reads nothing. What
follows `1.0`:
[RELEASES.md](https://github.com/socklove-eth/docs/blob/v1.0/RELEASES.md).

```
+---------------------------- Ethereum ----------------------------+
|   socklove.eth --addr--> Ring <SAFE_ADDRESS>    1-of-1 -> 2-of-2 |
|   <PAGE>.socklove.eth --contenthash--> <CID>                     |
+------------------------------------------------------------------+
        ^                                   |
        | Altar reads over RPC;             | A gateway fetches <CID>
        | your wallet sends                 | from IPFS: one HTML file
        |                                   v
+-------------------------- Your browser --------------------------+
|   Altar  -- Reads over RPC, signs in your wallet                 |
|   Sigil  -- Computes locally, sends nothing                      |
+------------------------------------------------------------------+
```

---

## 📄 Page

One [HTML](https://html.spec.whatwg.org/) file pinned on
🕸️ **[IPFS](https://ipfs.tech/)** under its **CID**, everything inlined: the
✨ **[Light](https://github.com/socklove-eth/docs/blob/v1.0/STYLE.md)**,
[page.css](https://github.com/socklove-eth/pages/blob/v1.0/page.css), the Pages'
shared stylesheet, its fonts, logo, favicon and
[JavaScript](https://tc39.es/ecma262/) bundle. Its `<meta>`
[Content-Security-Policy](https://developer.mozilla.org/en-US/docs/Web/HTTP/Reference/Headers/Content-Security-Policy)
allows script and style by hash alone, fonts and images as `data:`, and sets
`require-trusted-types-for 'script'; trusted-types 'none'`: every screen is
built from elements and text.

| Page | Network | Refuses to run |
|---|---|---|
| **[Sigil](https://sigil.socklove.eth.limo)** | None: `default-src 'none'`. | Framed or on a path gateway. |
| **[Altar](https://altar.socklove.eth.limo)** | `connect-src https: http://127.0.0.1:* http://localhost:*`: any [JSON-RPC](https://ethereum.org/developers/docs/apis/json-rpc/) endpoint, and loopback for a local chain. | Framed, on a path gateway, or from `file://`. |

A refusing Page shows *This Page cannot run here.* inside its shell and runs
nothing.

- **Rules:** [STANDARD.md](https://github.com/socklove-eth/pages/blob/v1.0/STANDARD.md).
- **Limits:** [SECURITY.md](https://github.com/socklove-eth/pages/blob/v1.0/SECURITY.md).

---

## 💒 Altar

### 🔎 Reading

Altar reads the Ring at the address it was built with, **with no wallet**: its
owners (`getOwners`), its **Threshold** (`getThreshold`) and its **Nonce**
(`nonce`).

While the Threshold is 1, Altar shows the
🧎 **[Proposal](https://github.com/socklove-eth/.github/blob/v1.0/RELEASE.md)**.
Once it is anything else, Altar shows Done and **stops reading the chain**,
except to await the receipt of a send. The yes then stays shown on every load,
whatever happens to the name.

At 1-of-1 it also checks the name: `socklove.eth` must resolve via
📛 **[ENS](https://ens.domains/)**, from the pinned resolver alone, to that
Ring. Otherwise, on any screen that reads the chain and can safely redraw, it
stops: *This Page no longer reads socklove.eth.* for a moved name, *Nothing
stands here yet.* for an unset one. A pinned Page never follows a moved name.
An endpoint you supplied may be the one that is wrong: Altar forgets it and
shows that line on the RPC screen, under its prompt.

At 1-of-1 it reads the Nonce every five minutes, and again when a hidden tab
returns; the watch rereads the rest only when the Nonce rises. It never redraws
over input, a wallet call or a message. The Ask and Yes buttons read the Nonce
again before they act, and redraw instead if it rose. A lower Nonce, from a
lagging node, is ignored.

### 🛰️ Endpoints

Altar reads over JSON-RPC: four seconds and one retry per endpoint, then the
next; the whole set retried up to three times. Their answer sets the chain,
⛓️ **[Ethereum](https://ethereum.org/)** or the local chain, and with it the
signing domain.

1. **The baked set** — The ten `RPC_URLS` in
[.env](https://github.com/socklove-eth/pages/blob/v1.0/.env), in order:
[README.md](https://github.com/socklove-eth/pages/blob/v1.0/README.md). Each is
held to the chain first reported, so one that later answers for another is
passed over; when none answers, the RPC screen below opens.
2. 🔧 **[Living Registry](https://github.com/socklove-eth/docs/blob/v1.0/REGISTRY.md)**
— Unless you supplied one, its record `rpc.endpoints`, read through the baked
set. Once an endpoint it names answers for the same chain, it serves ahead of
the baked set and the notice names it. One that answers for another chain, or
cannot be reached at any point, is passed over until the Page reloads. An empty
record or a failed read leaves the baked set.
3. **Yours** — The RPC screen asks *Enter your own RPC endpoint:* and offers the
Connect button; it takes https or loopback http. It opens when reading fails at
the start, or when the read before the Ask or Yes button acts meets a lost
connection or a wrong chain; an endpoint's own error at that point reads *It did
not go through.* instead. When every public endpoint fails, the screen adds *No
public RPC endpoint was reached.* Yours replaces the baked set for the tab, and
no record moves it. One that fails, or answers for a chain Altar does not run
on, is forgotten and its field emptied with the thorn (`.pricked`,
[STYLE.md](https://github.com/socklove-eth/docs/blob/v1.0/STYLE.md)); unless
the Connect button was just pressed, the screen also says *Your RPC endpoint
was not reached.*

The notice names the answering endpoint's host alone, as a copy target, and a
forgotten endpoint no longer: *☝️ The RPC endpoint, `<HOST>`, sees you ask.*

### 🪧 Screens

One at a time; the documents name each.

| Screen | When | Shows |
|---|---|---|
| **Reading** | Every load. | *Reading the chain…* |
| **Ask** | 1-of-1, opened without a signed link. | *Ask her to marry you and put the 💍 **Ring** on her finger.*, her address, the Ask button. |
| **Handoff** | The asker's signature recovers to an owner. | *🧦 **Sockthief**, will you marry me?*, the hash, the [QR code](https://www.iso.org/standard/83389.html). |
| **Answer** | A valid signed link at 1-of-1. | *Just say yes and put on the 💍 **Ring**.*, the hash, the Yes button. |
| **Waiting** | The Yes button sent, or a reload while that send stands. | *Waiting for the chain…* |
| **Done** | A Threshold other than 1. | *She said yes. The 💍 **Ring** is whole.* |
| **RPC** | Reading failed, or your endpoint read the name unset or moved. | A prompt for your own endpoint: *Enter your own RPC endpoint:*, the Connect button; *No public RPC endpoint was reached.*, *Your RPC endpoint was not reached.*, or what your endpoint read. |
| **Refusal** | A link no one can answer, a moved name read through the baked set or the record, an error, a frame, a path gateway or `file://`. | One line: *This Proposal cannot be answered.*, *This Page no longer reads socklove.eth.*, *Something went wrong.*, *This Page cannot run here.* |
| **Empty** | No Ring, or at 1-of-1 no resolver or address, read through the baked set or the record. | *Nothing stands here yet.* |

Done, Empty and every Refusal are final, except an unanswerable link's Refusal:
that one, like every screen that is not final, the RPC screen aside, gives way
to Done once the Ring is whole, where a redraw is safe. When the Nonce moves,
the Handoff returns to Ask and the Answer turns to Refusal. The RPC screen leads
back to Reading.

### 👛 Acting

- **The keys are the access control.** A wallet is asked for only when you
act. *Which wallet?* offers a button per announced wallet, by name, kept for
the tab. One on another chain is asked to switch: switched, the Page starts
over; declined, silence; unable, *Your wallet is not on the right chain.*
- **The Ask button** signs only for a checksummed address the Safe could add:
not zero, its sentinel, the Ring or an owner. Anything else is refused as
[STANDARD.md](https://github.com/socklove-eth/pages/blob/v1.0/STANDARD.md)
sets out. The Handoff shows only once the signature recovers to an owner; else
*It did not go through.*
- **Quiet errors:** a declined request or no shared account says nothing;
*It did not go through.* and *Something went wrong.* carry no raw reason. With
no wallet the screen says *No wallet.*, cleared once a wallet announces itself,
and pressing does nothing. A request already pending in the wallet reads *Your
wallet is asking…*, like any request.
- **Waiting:** once the Yes button sends, the screen reads *Waiting for the
chain…* until one of these:
  - Done, from the receipt of that send or of what replaced it, read in its own
block, or from a Nonce read.
  - The Answer again, after a revert, or a replacement or cancel seen during the
wait, with *It did not go through.* under the Yes button.
  - The Refusal, *This Proposal cannot be answered.*, if the Nonce rose, seen by
the wait or by a Nonce read.

  A replacement that lands unseen is waited for as a send never mined. A send
never mined keeps the wait while the tab is open and the Nonce is unmoved. A
reload waits again until, six minutes after the send, the chain does not know it
and the Nonce is unmoved; then the Answer returns. Six minutes is longer than a
private route holds a send by default.
- **Kept for the tab** in
[`sessionStorage`](https://developer.mozilla.org/en-US/docs/Web/API/Window/sessionStorage):
the supplied endpoint, the wallet and a sent Yes (its **SafeTxHash**, the
transaction and when), and the address asked across the reload a chain switch
causes; where the browser blocks it, memory keeps them while the Page is open.
The signed link is only on screen: a reload of the Handoff starts over at Ask.

### 🧎 Proposal

One **SafeTx**, `DELEGATECALL`ed into
[MultiSendCallOnly](https://github.com/safe-fndn/safe-smart-account/blob/v1.4.1/contracts/libraries/MultiSendCallOnly.sol),
gas and refund fields zero, so a failed inner call cannot spend the Nonce:

1. The Ring takes the label `sockthief`, so the resolver accepts its writes.
2. The resolver points it at her address.
3. The label goes to her (the Queen's 👑 **Crown**).
4. **Last**, at Threshold 1 —
`addOwnerWithThreshold(<SOCKTHIEF_ADDRESS>, 2)`.

### 🤝 Link

```
+--------------------------- Sockpusher ---------------------------+
|   Altar   -- Takes her address; the Ask button                   |
|   Wallet  -- Signs the SafeTx, off-chain                         |
|   Altar   -- Shows the hash and the QR code                      |
+------------------------------------------------------------------+
                                 |
                                 | QR code: <PAGE_URL>#<FRAGMENT>
                                 v
+--------------------------- Sockthief ----------------------------+
|   Altar   -- Recovers the signer; shows the hash                 |
|   Sigil   -- Both read their ten Marks aloud; she sends if equal |
|   Wallet  -- Sends execTransaction: the Yes button               |
+------------------------------------------------------------------+
                                 |
                                 | 1-of-1 -> 2-of-2
                                 v
+------------------------------ Ring ------------------------------+
|   Both owners; neither moves alone                               |
+------------------------------------------------------------------+
```

The asker's wallet signs the SafeTx off-chain, as
[EIP-712](https://eips.ethereum.org/EIPS/eip-712) typed data with
`eth_signTypedData_v4`. The fragment is the Ring's address, hers, the Nonce and
that signature, as [JSON](https://www.rfc-editor.org/rfc/rfc8259.html) in
[base64url](https://www.rfc-editor.org/rfc/rfc4648.html#section-5), good until
the Nonce moves. It **leaves only as a QR code**, query dropped, with the
SafeTxHash to compare.

The answering Page shows the hash and the Yes button, which executes. It
refuses with *This Proposal cannot be answered.* a fragment that is unreadable
(a broken checksum included), names another Ring address or Nonce, or carries
a signature that is missing, malformed or not an owner's.

Any account but the one added gets *Your wallet is not on the right
account.*, the Page's own check: at Threshold 1 the asker's signature alone
satisfies the Ring.

---

## 👀 Sigil

Altar prints the SafeTxHash, which most wallets do not show; Sigil turns it into
ten numbered
🧿 **[Marks](https://github.com/socklove-eth/pages/blob/v1.0/marks/marks.json)**,
spoken to a screen reader once, never translated. **Say them aloud; she sends
only if both screens agree.** The asker's own protection is the name and the
CID.

```
                    <SAFE_TX_HASH>, 64 lowercase hex, no 0x
                                 |
                                 v
+------------------------- PBKDF2-SHA-256 -------------------------+
|   Password     "socklove.eth:check:v1:" + hash, UTF-8            |
|   Salt         "socklove.eth:check:v1:salt", UTF-8               |
|   Iterations   4,000,000                                         |
|   Output       10 bytes                                          |
+------------------------------------------------------------------+
                                 |
                                 | Each byte >> 2: an index, 0-63
                                 v
+--------------------------- marks.json ---------------------------+
|   Ten Marks, shown numbered 1 to 10, in byte order               |
+------------------------------------------------------------------+
```

Anyone can recompute them without Sigil, with
[Python](https://docs.python.org/3/), from a checkout of the Pages repository
and its
[marks.json](https://github.com/socklove-eth/pages/blob/v1.0/marks/marks.json):

```bash
python3 - <SAFE_TX_HASH> marks/marks.json <<'EOF'
import hashlib, json, sys
h = sys.argv[1].lower().removeprefix('0x')
key = hashlib.pbkdf2_hmac('sha256', f'socklove.eth:check:v1:{h}'.encode(),
                          b'socklove.eth:check:v1:salt', 4_000_000, 10)
marks = json.load(open(sys.argv[2]))
for n, b in enumerate(key, 1):
    print(n, *marks[b >> 2])
EOF
```

- **Slow on purpose:** a
[PBKDF2](https://www.rfc-editor.org/rfc/rfc8018.html) attempt costs about half
a second on a laptop.
- **Sixty bits guard a fixed hash:** matching another hash's Marks takes about
2⁶⁰ attempts, two chosen together about 2³⁰, so Sigil compares only a
transaction one side composes — in the Proposal, the Ring's state and the
address the asker types.
- **Numbered:** each Mark shows its place, 1 to 10, so two screens laid out
differently are read in the same order.
- **Words over pictures:** each Mark is one emoji from
[Emoji `13.0`](https://www.unicode.org/emoji/charts-13.0/emoji-released.html) or
earlier, no joiners or skin tones, its word naming what it shows; no word
repeats, prefixes another, sits one edit from another or rhymes with another on
its stressed syllable, and no two of one length end in the same three letters.
- **Refusals are silent:** a paste, Enter, or 64 typed digits that are no hash
(zeroes included) empty the field with the thorn, marked invalid until the
field next changes or takes a paste. Any insertion but a paste counts as
typing. Entering the hash already on screen starts no second derivation. One
error speaks, when
[Web Crypto](https://developer.mozilla.org/en-US/docs/Web/API/Web_Crypto_API)
is missing or fails: *This browser cannot read the Marks.*
- **Pinned forever:** the password's prefix, the salt, the iterations and the
Marks in order.

---

## 📏 Invariants

Each is held by tests.

- **No request but the chain's**, and no navigation:
[STANDARD.md](https://github.com/socklove-eth/pages/blob/v1.0/STANDARD.md).
- **One SafeTx builder** feeds the hash shown, the signature and the execution.
- **Nothing that acts comes from data:** name, sub-name label, registry,
resolver, MultiSendCallOnly and the Ring come from the committed
[.env](https://github.com/socklove-eth/pages/blob/v1.0/.env); off-chain lookups
are off; the chain is the endpoints' answer, and a signature on the local chain
is worthless on Ethereum.
- **A signature passes only with recovery byte 27 or 28**, and a low `s`.
- **One set of bytes** runs on Ethereum and the local chain, which carries its
code at its addresses.
- **The CID is a function of the source alone.**
  - **Building:** [README.md](https://github.com/socklove-eth/pages/blob/v1.0/README.md).
  - **Verifying:** [RELEASES.md](https://github.com/socklove-eth/docs/blob/v1.0/RELEASES.md).
