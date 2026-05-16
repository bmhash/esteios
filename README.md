# Brain Drafts

**Notas para a minha filha** — Um livro filosófico estruturado em torno da Paideia e da tradição estóica.

## Sobre o Projecto

Este é um livro vivo, escrito ao longo do tempo, organizado em três círculos concêntricos:

- **Círculo I — Logos** (O Eu Interior)
- **Círculo II — Ethos** (Com os Outros)
- **Círculo III — Cosmos** (No Mundo)

Inspirado nas *Meditações* de Marco Aurélio, no *Encheirídion* de Epicteto, e na *Paideia* de Werner Jaeger.

## Estrutura Técnica

```
/chapters       → Capítulos finalizados (15 no total)
/fragments      → Notas em bruto, rascunhos, sementes
/sources        → Referências, citações, notas de leitura
/styles         → Design minimalista estóico
/data           → Plano filosófico e técnico original
```

## Workflow de Escrita

1. **Escrever** em Markdown (`.qmd` files)
2. **Commit** para Git
3. **Push** para GitHub
4. **Deploy automático** via GitHub Actions → GitHub Pages

## Comandos Locais

```bash
# Preview local
quarto preview

# Render HTML
quarto render

# Render PDF (para impressão)
quarto render --to pdf

# Render ePub
quarto render --to epub
```

## Deploy

O livro é automaticamente publicado em:
**https://bmhash.github.io/drafts/**

Cada push para `main` desencadeia uma nova build via GitHub Actions.

## Princípios de Design

- **Longevidade acima da tendência** — HTML simples, sem JavaScript
- **Escrita em primeiro lugar** — Markdown puro, sem fricções
- **Portabilidade** — HTML, PDF, ePub da mesma fonte
- **Tipografia clássica** — EB Garamond, margens generosas, espaçamento amplo
- **Sem rastreamento, sem comentários, sem partilha social**

---

*«A posse que ninguém pode tirar ao homem é a paideia.»* — Menandro
