# Plano — Livro 1

Livro 1 da série (título de trabalho). Este arquivo é a **fonte única**
dos títulos e da numeração dos capítulos: `make outline BOOK=livro-1` cria
ou atualiza os arquivos em `books/livro-1/chapters/`, sem nunca tocar no
corpo já escrito.

**Não rodar `make outline` enquanto as vagas tiverem títulos provisórios** —
o scaffolder cria um arquivo por vaga.

---

## A premissa — escolhida

Uma mulher descobre que o avô a prometeu ao Encante, a cidade dos encantados
no fundo do rio, e que a dívida vence no dia em que ela fizer vinte e cinco anos.
O emissário mandado do fundo para buscá-la é o homem por quem ela se apaixona,
e ele tem um preço próprio a pagar se voltar sem ela.

Escolhida pelo autor em 2026-10-06, entre três (as outras: *Os filhos do boto*
e *A balsa do São Francisco*). É o pacto com o reino encantado, o tropo que o
leitor de romantasia mais procura, contado com encantaria brasileira. E dá ao
livro um relógio: a data em que a dívida vence.

- **Protagonista:** uma advogada de 24 anos, criada longe do rio. Volta para
  o enterro do avô semanas antes do aniversário e lê o pacto como um contrato,
  procurando brecha. **Ana Jaci**: Ana em São Paulo, Jaci para o avô. O
  livro a leva de um nome ao outro.
- **Onde:** o Baixo Tapajós, no oeste do Pará: Santarém, Alter do Chão, a
  várzea e as comunidades ribeirinhas em volta.
- **Quando:** o presente (2026), nas semanas entre o enterro, no fim de abril,
  e o aniversário, no começo de junho, perto do pico da cheia. Dois relógios: a
  data em que a dívida vence e a água que sobe.

Decidido em 2026-10-06; o autor aceitou as três recomendações. Advogada, porque
um pacto lido como contrato dá à protagonista um motor de enredo (a lei dela
contra a lei do fundo) e uma língua afiada. De fora, porque é a única que tem
licença para se espantar com o rio (`CLAUDE.md`, *O encanto na página*). O
Tapajós, porque lá o boto e os encantados são conversa de todo dia. A cheia,
porque a água subindo é o relógio visível.

**O Çairé fica fora deste livro.** A festa, com a disputa dos botos Tucuxi e
Cor-de-Rosa, é no terceiro fim de semana de setembro, na vazante, e o livro se
passa na cheia (ver `references.md`). Pode voltar como lembrança da infância
dela, ou num livro seguinte.



## Os quatro arcos — aprovados (2026-10-06)

Cada arco é uma parte, e cada parte muda a protagonista. O estado em que ela
entra e sai de cada arco fica em `bible.md`, em *Protagonista*.

| Parte | O arco | Capítulos |
|---|---|---|
| I — A HERANÇA | Ana volta para o enterro do avô, acha o pacto no caderno dele e conhece Tomé no velório. Trata tudo como golpe. No fim do arco o rio prova que é real, levando alguma coisa na frente dela. | 5 |
| II — O PRAZO | Ana trabalha o caso: ouve o rio, aprende as regras do Encante, negocia com Tomé, que as regras obrigam a ficar perto dela. Faíscas, desejo que nenhum dos dois quer. Descobre que a vida dela é a coisa emprestada. O primeiro beijo. | 4 |
| III — A CHEIA | A água chega ao pico e o Encante aperta a vila. Viram amantes. Ela descobre que a liberdade dele depende de ela descer por vontade própria. A mãe chega e conta: o avô não se afogou, entrou no rio para se oferecer no lugar dela. | 4 |
| IV — O FUNDO | No aniversário, ela entra na água por escolha e defende a própria causa no tribunal do Encante. Tomé depõe contra a Dona. A dívida foi cobrada duas vezes; quem cobra o que já recebeu devolve em dobro. Duas vidas voltam: a dela, livre, e a dele, humana. | 5 |

### A espinha, em uma linha por peça

- **O pacto é um empréstimo, não uma venda.** Ana nasceu morta, numa cheia; o
  avô implorou ao rio, e o Encante emprestou a ela vinte e cinco anos de vida.
  Anular o contrato anula a vida dela. É a armadilha da advogada.
- **O Encante só leva quem entra na água por vontade própria.** O trabalho de
  Tomé é fazê-la querer descer, que é exatamente a lenda do boto. Ele se recusa
  a usar o encanto nela (`CLAUDE.md`: *o encanto nunca é consentimento*).
- **A recompensa dele é a perda dela.** Se a levar, Tomé recebe de volta a vida
  humana que o Encante tomou dele menino.
- **O avô já pagou.** Em abril ele entrou no rio para ir no lugar dela, e a Dona
  aceitou. Cobrar a neta de novo é cobrar duas vezes.
- **O clímax é a profissão dela.** Investiga no II, negocia no III, ganha um
  julgamento no IV. A lei do Encante tem a mesma regra do art. 42 do CDC (ver
  `references.md`): quem cobra o indevido devolve o dobro, salvo engano
  justificável. A defesa da Dona é o engano; o depoimento de Tomé prova que ela
  sabia. É por isso que ele precisa escolher Jaci contra a própria liberdade.
- **A escolha final.** O dobro são duas vidas. Uma é a dela. A outra poderia
  ser a do avô; ele, já encantado, pede que ela escolha Tomé. Ela escolhe.
- **O preço do final feliz.** Tomé perde o rio e a vida longa, e envelhece com
  ela. Jaci fica presa ao rio, e fica por escolha: abre um escritório em
  Santarém para as famílias ribeirinhas. O Encante continua lá embaixo.

### Elenco principal

- **Ana Jaci**, 24, advogada em São Paulo.
- **Tomé**, o emissário: linho branco, chapéu que nunca tira. Foi humano.
- **A Dona do Fundo**, que governa o Encante e é dona da dívida. Invenção do
  livro, não uma entidade real.
- **A mãe**, que tirou Ana do rio ainda bebê e nunca disse por quê.
- **O avô**, morto em abril; volta, encantado, no fim.

## A decidir pelo autor

- [[?autor: título — decidido em 2026-10-06 que fica para o fim, depois do rascunho completo]]
- [[?autor: tamanho — recomendação: 75.000 a 90.000 palavras, a faixa da romantasia]]

---

## Formato de cada capítulo

Copiar o bloco abaixo por capítulo. `make outline` lê os campos em negrito;
`Fios`, `Planta`, `Paga` e `Elenco` são listas separadas por vírgula.

    ### 1. Título do capítulo
    - **POV** — quem conta
    - **Quando** — 2140-03-14 — manhã (a data ordenável vem primeiro)
    - **Onde** — lugar
    - **A ideia** — o capítulo em uma frase
    - **A virada** — o que muda até o fim dele
    - **Fios** — fio-um, fio-dois
    - **Planta** — semente-um
    - **Paga** — semente-plantada-antes
    - **Elenco** — nome-um, nome-dois

---

## PARTE I — A HERANÇA

*Arco:* ver a tabela de *Os quatro arcos*.

### 1. Arco I, capítulo 1 — título a decidir
- **A ideia** — [[?autor]]

### 2. Arco I, capítulo 2 — título a decidir
- **A ideia** — [[?autor]]

### 3. Arco I, capítulo 3 — título a decidir
- **A ideia** — [[?autor]]

### 4. Arco I, capítulo 4 — título a decidir
- **A ideia** — [[?autor]]

### 5. Arco I, capítulo 5 — título a decidir
- **A ideia** — [[?autor]]

## PARTE II — O PRAZO

*Arco:* ver a tabela de *Os quatro arcos*.

### 6. Arco II, capítulo 1 — título a decidir
- **A ideia** — [[?autor]]

### 7. Arco II, capítulo 2 — título a decidir
- **A ideia** — [[?autor]]

### 8. Arco II, capítulo 3 — título a decidir
- **A ideia** — [[?autor]]

### 9. Arco II, capítulo 4 — título a decidir
- **A ideia** — [[?autor]]

## PARTE III — A CHEIA

*Arco:* ver a tabela de *Os quatro arcos*.

### 10. Arco III, capítulo 1 — título a decidir
- **A ideia** — [[?autor]]

### 11. Arco III, capítulo 2 — título a decidir
- **A ideia** — [[?autor]]

### 12. Arco III, capítulo 3 — título a decidir
- **A ideia** — [[?autor]]

### 13. Arco III, capítulo 4 — título a decidir
- **A ideia** — [[?autor]]

## PARTE IV — O FUNDO

*Arco:* ver a tabela de *Os quatro arcos*.

### 14. Arco IV, capítulo 1 — título a decidir
- **A ideia** — [[?autor]]

### 15. Arco IV, capítulo 2 — título a decidir
- **A ideia** — [[?autor]]

### 16. Arco IV, capítulo 3 — título a decidir
- **A ideia** — [[?autor]]

### 17. Arco IV, capítulo 4 — título a decidir
- **A ideia** — [[?autor]]

### 18. Arco IV, capítulo 5 — título a decidir
- **A ideia** — [[?autor]]
