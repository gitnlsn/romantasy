# Série nova

Manuscrito em Markdown; EPUB pronto para a KDP e PDF pronto para impressão do
outro lado. Mesma cadeia de ferramentas de *Quarenta dias úteis*, *Manual da
Vida* e *What Remains*.

    make deps                  # uma vez, no macOS
    make                       # constrói o livro 1
    make check                 # preflight contra o que a KDP recusa
    make marcadores            # o que ainda está em aberto
    make release               # constrói e confere tudo (pt + en)
    make traducao              # capítulos em inglês atrás do original
    make new-book SLUG=<slug> TITLE="..."   # o próximo livro

| # | Livro | `BOOK=` | Edição em inglês | `BOOK=` |
|---|---|---|---|---|
| 1 | *a decidir* | `livro-1` | *to be decided* | `book-1` |

## Layout

    books/<slug>/
      book.yaml              metadados, formato, número na série, anúncio na KDP
      front/                 o que vier antes             (fólios romanos)
      chapters/              o romance                    (fólios arábicos)
      parts/                 aberturas das 4 partes
      back/                  o que vier depois
      illustrations/masters/ originais em alta, um por parte
    docs/
      series.md              o que é da série: nome, ordem, forma comum
      translation-en.md      as regras das edições em inglês
      kdp-upload.md          o passo a passo do upload
      <slug>/
        outline.md           premissa, os 4 arcos, fonte única dos capítulos
        bible.md             o mundo daquele livro
        timeline.md          a cronologia
        references.md        o que é real, e onde foi conferido
        translation-en.md    títulos, glossário e frases fixas em inglês
      _modelo/               os arquivos em branco, para um livro novo
    shared/                  template de impressão, capa, CSS do EPUB, fontes
    scripts/                 build, gates, digest, stats, scaffolders
