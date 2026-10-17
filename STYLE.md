# SockLove Docs Style

> Two standards: how SockLove is written, and how it looks.

---

## 🖋️ Ink

The 🖋️ **Ink** guides every Markdown file and every
📄 **[Page](https://github.com/socklove-eth/pages/tree/v1.0)**, loosely and with
judgement. What a Page must do and refuse:
[STANDARD.md](https://github.com/socklove-eth/pages/blob/v1.0/STANDARD.md).

1. **Titles follow the path from
🧦💜 [SockLove](https://github.com/socklove-eth)**:
`# SockLove <REPOSITORY> <DIRECTORY> <FILE>`, less any segment that says nothing
new; a README takes its place's name. The profile's
[README.md](https://github.com/socklove-eth/.github/blob/v1.0/profile/README.md),
`# SockLove`, shows the current release's
🖼️ **[Plate](https://github.com/socklove-eth/.github/blob/v1.0/profile/assets/plate.jpg)**,
captioned, between rules after its tagline.
2. **A one-line tagline** follows the title, in a blockquote.
3. **A rule opens each section:** `---` before each `##`. A heading leads with
one symbol: a term's own only when the section is about that term; else a
plain, descriptive one no term wears.
4. **Sentence case for headings.** A capital starts each sentence, cell, list
item and code-block note; a full stop ends each sentence, cell and list item,
but not a label or a code aside. Code keeps its own case. A version sits in
backticks, bare, with as many parts as its project gives it: `1.4.1`, `26`,
`1.0`; never `v1.4.1`.
5. **SockLove terms are proper nouns**, lowercase only in code, a tagline, and
where *page* means any web page.
6. **Mark a SockLove term at its first mention** in a file: its symbol, then
the term in bold, as a bold link once its subject exists.
   - Symbols mark SockLove's people, places, objects, events and the networks it
stands on.
   - Borrowed terms, from larger networks, take no symbol: bold when the reader
must know them, capitalised as
[LEXICON.md](https://github.com/socklove-eth/docs/blob/v1.0/LEXICON.md) spells
them, backticks for a field, key or identifier, else plain.
   - Titles, taglines and headings are no first mention; a row's or item's
leading label is one, and carries the mark; in
[LEXICON.md](https://github.com/socklove-eth/docs/blob/v1.0/LEXICON.md) the mark
sits on the term's own row.
   - A term's symbol, once in
[LEXICON.md](https://github.com/socklove-eth/docs/blob/v1.0/LEXICON.md), is
pinned to it for good: nothing else takes it. A new term may take a symbol only
headings have used; from then it is pinned.
🧿 **[Marks](https://github.com/socklove-eth/pages/blob/v1.0/marks/marks.json)**
are excepted: 👀 **[Sigil](https://sigil.socklove.eth.limo)**'s 64 are a
vocabulary of their own.
   - Only 🧦💜 SockLove and 😘👌 **Sockpusher's Kiss** wear two symbols.
   - A file never links its own subject: the profile's
[README.md](https://github.com/socklove-eth/.github/blob/v1.0/profile/README.md)
leaves SockLove unlinked, the Pages'
[README.md](https://github.com/socklove-eth/pages/blob/v1.0/README.md) its
Pages.
   - Every emoji SockLove shows is
[Emoji `13.0`](https://www.unicode.org/emoji/charts-13.0/emoji-released.html) or
earlier, by [Unicode](https://www.unicode.org/)'s
[emoji-test.txt](https://unicode.org/Public/emoji/13.0/emoji-test.txt).
7. **Link a SockLove term's network or project to its home page** at first
mention; tools, standards, protocols and licences to their documentation, rule
6's borrowed terms aside.
8. **Link a file or directory by name**, never by its path, at every mention,
at this release:
[RELEASES.md](https://github.com/socklove-eth/docs/blob/v1.0/RELEASES.md).
9. **Keep it short.** One fact, one place; the rest point to it. Contributing
and reporting live in `.github`; a code repository adds its own
[SECURITY.md](https://github.com/socklove-eth/pages/blob/v1.0/SECURITY.md), its
threat model. Describe what a thing does, within
[RELEASES.md](https://github.com/socklove-eth/docs/blob/v1.0/RELEASES.md).
10. **Keep lines to 80 columns**, an emoji counting two, except tables, code
blocks, and a line whose only overflow is one link, address or code span, with
its label and punctuation.
11. **Draw diagrams in ASCII**, in a fenced block.
12. **Prefer few files, one word each**: one English word in capitals, in the
repository's root; a sub-directory only when files grow many or a part wants a
narrower scope. Reviews take `<SCOPE>_<VERSION>`.

A README carries two badges under its title: release and licence.

### 🎙️ Voice

- **Short beats, hard periods.** Second person, present tense, imperative;
sacred and carnal at once.
- **Caption a value before showing it**, in the reader's terms.
- **A button says what it does**, without narrating the wallet or naming a
function, led by one emoji, mythic and telling what it does; any emoji, a
term's symbol included. Elsewhere a button is named plainly, without its emoji:
the Ask button.
- **Plain words**, a SockLove term only where needed; state is told in words.
- **On a screen, mark a term at its first mention** in a sentence, per rule 6;
errors, labels, placeholders, the tab title and the header stay plain.
- **A Page speaks only when the reader cannot otherwise know what they
need:** never what they just did, never a raw reason, never a guess.
  - A declined request says nothing.
  - A refused field empties and shows the thorn (`.pricked`,
[light.css](https://github.com/socklove-eth/pages/blob/v1.0/light/light.css)).
  - A screen the chain has moved is drawn afresh.
  - A line under the button asks something of the reader.
  - A whole-screen line stands alone, where the Page can go no further.

---

## ✨ Light

Every surface wears the ✨ **Light**,
[light.css](https://github.com/socklove-eth/pages/blob/v1.0/light/light.css),
byte for byte. Its names are images that say what a thing means; the tables
say what each styles, and the image it holds. It lays out no page: a surface's
own stylesheet, in plain names, places things and mixes shades with
`color-mix()`, never adding them.
[light.test.ts](https://github.com/socklove-eth/pages/blob/v1.0/light/light.test.ts)
holds the names, their order and the rules.

| Colour | For | Image |
|---|---|---|
| `--night` `#000` | The ground everything stands on. | The night every scene is set in. |
| `--ink` `#bbb` | Words, unless another colour says more. | The ink the words are written in. |
| `--spark` `#FFF5EA` | What must be seen exactly: read, compared, taken. | Sparks. |
| `--candle` `#FFB547` | Warmth around an act, never the act. | Candlelight, and gold. |
| `--heart` `#FF3355` | An act that binds. | The burning heart. |
| `--flame` `#FF2ECF` | That act, close at hand. | Its flames. |
| `--bond` `#B45CFF` | What only two can do as one, and the act that joins them. | The sock, where red meets blue. |
| `--crossing` `#3D9BFF` | Going, choosing, and where you are. | The blue sock across the breach. |
| `--seal` `#6FD3FF` | What is done: taken, kept, confirmed. | The seal. |
| `--thorn` `#FF7A59` | A refusal, and nothing lost. | The roses' thorn. |
| `--spectrum` | Five colours in one sweep: candle, heart, flame, bond, crossing. | The candlelight, through the heart and its flame, into the bond, to the crossing. |

| Name | For | Image |
|---|---|---|
| `--carved` | Names, in [Cinzel](https://fonts.google.com/specimen/Cinzel), then Georgia, then a serif. | Names are carved. |
| `--spoken` | Words, in [Outfit](https://fonts.google.com/specimen/Outfit), then the system sans-serif. | Words are spoken. |
| `--cipher` | Hashes and code, in the system monospace. | Hashes are cipher. |
| `.step` | Any press: at least 44px tall, 11px capitals spaced 0.3em, a 1px border, transparent; 35% when disabled. | A step. |
| `.vow` | A press that binds: `--heart`, turning `--flame` with a glow. | A vow. |
| `.way` | A press that goes or chooses: `--crossing`, brightening toward `--spark`. | A way. |
| `.crossroads` | Equal choices, side by side: centred in 150px columns 14px apart, read in order. | Every way as wide as the next. |
| `.quill` | Where a hand writes: `--spark` in `--cipher`, glowing `--crossing` on focus, 16px under a coarse pointer so a phone does not zoom. | A quill. |
| `.pricked` | Writing refused: a `--thorn` flash, over the focus glow. | Pricked by the thorn. |
| `.inscription` | What is read and taken, exactly: its ⧉ mark at a fixed width so nothing shifts. | An inscription. |
| `.sealed` | An inscription, taken: ⧉ becomes a `--seal` ✓. | Sealed. |
| `.thorn` | A word that refuses, 12px. | A thorn. |
| `.bond` | A word of what two did as one. | A bond. |

**Nothing read wears the action's colour:** a value is plain grey, its copy
mark `--spark`, and it brightens under the pointer. A reader who asks for
reduced motion gets none.
