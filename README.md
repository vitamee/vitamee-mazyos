# Vitamee — Sistema operacional do negócio

> "Vitamina para sua melhor versão!"

Marca de suplementos (gummies e gotas) dos sócios **Luan** e **Natália**, rodando sobre o **MazyOS** dentro do Claude Code. Foco em qualidade, sabor e palatabilidade — pra levar energia, equilíbrio, foco e bem-estar no dia a dia.

## Como o sistema pensa
- **`_memoria/`** é o cérebro — quem é a empresa, como ela fala, o foco do momento. O Claude lê antes de cada resposta.
- **`identidade/`** é o rosto — paleta (carvão + verde vital + branco), logo e manual de marca. Tudo que o sistema gera respeita isso.
- O resto são as frentes de trabalho, versionadas neste repositório.

## Mapa de pastas
| Pasta | O que é |
|---|---|
| `_memoria/` | empresa, preferências, estratégia |
| `identidade/` | design-guide, logo, manual de marca |
| `produtos/` | catálogo, fichas, precificação |
| `marketing/` | conteúdo — `instagram/`, `trafego-pago/` |
| `site/` | site vitamee.br |
| `vendas/` | funil, scripts, pós-venda |
| `financeiro/` | custos, fluxo, metas |
| `dados/` | CSVs/planilhas pra análise |
| `saidas/` | documentos pontuais |
| `agentes/` | prompts/conhecimento dos agentes Vitamee |
| `templates/` | modelos do MazyOS |
| `_referencias/bull/` | material da Bull (outro negócio do Luan), só referência |
| `.claude/skills/` | as 15 skills do MazyOS |

## Como usar
- `/abrir` no começo de cada sessão pra carregar o contexto
- skills de conteúdo: `/carrossel`, `/publicar-tema`, `/seo`
- ads: `/anuncio-google`, `/relatorio-ads`
- `/salvar` faz commit + push no GitHub

## Pendências
- [ ] Tabela de produtos + fornecedores pra mineração (demanda × margem)
- [ ] Versão do logo pra fundo escuro / circular em `identidade/`
