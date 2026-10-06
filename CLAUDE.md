# CLAUDE.md

Production repo for a **new series of novels** by Íris Gradim, after *What
Remains* (`../science-fiction`). Each book lives in `books/<slug>/` and has its
own planning docs in `docs/<slug>/`. The Markdown manuscript builds to a
KDP-ready EPUB and a print-ready PDF, with the same toolchain as *Quarenta dias
úteis* (`../artificial-intelligence-a-dystopia`), *Manual da Vida* and *What
Remains*.

## The series: nothing decided yet

Genre, premise, number of books and series name are all open. They live in
`docs/series.md` as `[[?autor: …]]` markers, so `make marcadores` keeps asking.

There is one **seed book**, `livro-1`, with its English edition `book-1`. Both
slugs are placeholders that exist so the build and `make new-book` have
something to inherit from. When the book gets its real title, rename
`books/<slug>/`, `docs/<slug>/`, `slug:` in its `book.yaml`, the `source:`
paths in the English edition, and `BOOK ?=`, `SERIES` and `TRANSLATIONS` in the
Makefile. Do it all at once.

How the author works (from the earlier books): open questions are settled as
multiple-choice with a recommended option. Once the plan and a sample chapter
are approved, the whole book is drafted in one go for a single review pass. When
the author delegates a decision, take it, record the reasoning in the outline,
and say what was decided.

If the series turns out to be science fiction, carry over the *O futuro na
página* rules from `../science-fiction/CLAUDE.md`. Otherwise, write this
genre's equivalent rules here once the genre is chosen.

## O mundo é canônico — docs/<slug>/bible.md

**A chapter may invent, but the invention is not real until it is written
down.** When a draft invents something, add it to `docs/<slug>/bible.md` in
the same session, or leave `[[?mundo: …]]` in the prose. `make marcadores` will
not let that chapter reach `revised` or `final` while the marker stands.
Anything the book asserts about the real world goes in `docs/<slug>/references.md`
or is marked `[[?fato: …]]`.

Each arc must **change the protagonist**: they leave each part a different
person than they entered it, and the change is recorded under *Protagonista*
in that book's `bible.md`.

## Promessa e pagamento

Every chapter declares its setups and payoffs in front matter, as slugs:

    seeds: [porta-do-porao, o-nome-de-vera]
    pays:  [cartao-de-acesso]

`make fios` fails the build on a payoff whose seed is planted nowhere, or later
in reading order, or in the same chapter. Threads are reported, never gated.

## Ponto de vista, tempo e continuidade

`pov:`, `when:` and `where:` are the continuity record. Lead `when:` with a
sortable date so `make digest --tempo` can flag jumps backwards. `cast:` lists
who is on the page; `make digest --elenco` shows who has gone missing.

**Never write a chapter number into this file, into a skill, or into prose.**
Refer to chapters by title here, and by `{{cap:slug}}` in the manuscript.

## Diálogo

Dialogue is set the Brazilian way: each speech on its own line, opening with a
**travessão and a space** (`— `). Never use quotation marks or a hyphen.

    — As mãos eram minhas.

A line opening with `- `, `– ` or `-- ` is a Markdown list item and prints as a
bullet. `make marcadores` fails on it (`lint_dialogue` in `scripts/check-claims.py`).

## Front and back matter

- **Antes de começar** (front) says plainly that Íris Gradim is an AI and
  describes the human's role in choosing and directing the book, following the
  pattern of *Quarenta dias úteis*.
- **Sobre a autora** (back) keeps "Trabalha sob direção humana." and **three
  debts**, all to real works or real research the book draws on. It **never
  mentions or credits the person who directed the book**.

## Language: the English editions

Portuguese (pt-BR) is the primary edition. Printed labels come from `labels:`
in `book.yaml`. Each book has an **English edition, a separate book** (US
English).

- **The Portuguese is canon.** Docs are never translated. Each English chapter
  has the same filename as its source, Portuguese planning notes in its front
  matter, and `source:` + `source_sha:`. **`make traducao`** lists English
  chapters whose source changed, and `make release` stops on a stale one.
- Rules: `docs/translation-en.md` (series) and `docs/<source-slug>/translation-en.md`
  (titles, glossary, fixed sentences, *Found in the Portuguese*).
- Start a chapter with `scripts/translation-header.py`. **Revise the Portuguese
  first, then carry the change into the English** and restamp:
  `python3 scripts/check-translation.py <english-slug> --stamp <file>`.
- The English books share the Portuguese art through an `illustrations` symlink.

## Structure and conventions

- `docs/<slug>/outline.md` is the single source for that book's chapter titles
  and numbering. `make outline BOOK=<slug>` creates missing chapter files and
  refreshes planning notes; it never touches a written body. **Don't run it
  while the slots still carry placeholder titles**, because it would create one
  file per placeholder.
- `docs/<slug>/bible.md` is that book's world, `timeline.md` its chronology in
  story order, and `references.md` what is real.
- `docs/_modelo/` holds the blank templates; `make new-book SLUG=…` copies them
  into a new `docs/<slug>/`. Nothing in `_modelo/` is read by the gates.
- Planning notes (`pov`, `when`, `where`, `premise`, `turn`, `threads`, `seeds`,
  `pays`, `cast`, `status`) live in chapter front matter; the build strips them.
  `status:` goes `outline` → `draft` → `revised` → `final`, by hand.
- Part openers live in `books/<slug>/parts/`. Their `part:` string must match
  the `## PARTE …` heading in that book's outline exactly (`I — PRIMEIRO ARCO`).
  Rename both together.
- Chapter bodies: `##` for section heads (rarely), `---` for a scene break,
  never an `#` heading.
- Illustrations are part openers only, one master per part in
  `illustrations/masters/`, matched by the part's `illustration:` field. A
  placeholder is generated until the art exists.
- The build supports the `::: {.registro}` block (a set-apart document such as
  a log, a letter or a transmission).
- Covers are typographic, from `shared/print/cover.typ`, with a palette per
  book under `cover:` in `book.yaml` (`bg`, `ink`, `accent`, hex). The seed's
  palette is a neutral placeholder.
- `dist/` is never committed. Research material goes in `sources/` (untracked);
  only `.md` records of it are committed.

## Commands

Every target takes `BOOK=<slug>`; the default is `livro-1`.

    make                 # build the book (epub + interior + cover)
    make books           # build every book
    make release         # build + check the series, list the upload files (BOOK=… for one)
    make release-en      # the same, English editions only
    make check           # KDP preflight + both manuscript gates
    make fios            # setups without payoffs, payoffs without setups
    make marcadores      # unresolved [[?...]] markers (the book + docs/<slug>/ + docs/series.md)
    make traducao        # English chapters behind their Portuguese source
    make digest          # whole-novel map: pov, time, threads, cast
    make stats           # word counts, pacing, POV balance
    make outline         # docs/<slug>/outline.md -> chapter files
    make new-book SLUG=… # the next book in the series
    make watch           # rebuild the print PDF on every save

**`vale` is not a gate** (English linters, Portuguese manuscript; see
`.vale.ini`). Never report it as passing or failing.

## Template gotchas, already solved: do not "fix" them

Inherited from *Quarenta dias úteis*; the comments in
`shared/print/template.typ` explain each:

1. Recto breaks use `pagebreak(to: "odd")`. Do not reintroduce hand-computed
   page parity from `here().page()`.
2. Running heads and blank-page detection query elements; chapter numbers are
   passed as arguments. Do not convert either to `state`.
3. In the EPUB, a part opener's figure comes *after* the `<h1>`.
4. Only the vendored Libertinus faces are guaranteed to embed; KDP rejects a
   PDF with an unembedded font.
