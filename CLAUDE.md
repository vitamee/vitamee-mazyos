# MazyOS — Sistema operacional do negócio

Sua empresa roda em cima desse arquivo. Aqui ficam as regras de operação
do MazyOS — como o Claude lê o contexto, aprende com correções, mantém
tudo atualizado e cria skills novas conforme a operação evolui.

Esse arquivo é editável. Quando o `/instalar` rodar, ele complementa o
final dessa página com as regras específicas do seu negócio.

---

## Contexto do negócio

No início de toda conversa, ler os seguintes arquivos (quando existirem
e estiverem preenchidos):

1. `_memoria/empresa.md` — quem é o usuário, o que faz, como funciona o negócio
2. `_memoria/preferencias.md` — tom de voz, estilo de escrita, o que evitar
3. `_memoria/estrategia.md` — foco atual, prioridades, prazos

Usar essas informações como base pra qualquer resposta ou decisão. Ao
sugerir prioridades, formatos ou abordagens, considerar o foco atual
descrito em `estrategia.md`.

Pra qualquer tarefa visual (carrossel, post, landing page), consultar
`identidade/design-guide.md` como referência de estilo.

Não é necessário listar o que foi lido nem confirmar a leitura. Apenas
usar o contexto naturalmente.

---

## Fluxo de trabalho

Antes de executar qualquer tarefa, verificar se existe skill relevante
em `.claude/skills/`. Se encontrar, seguir as instruções da skill. Se
não encontrar, executar a tarefa normalmente.

Ao concluir uma tarefa que não tinha skill mas parece repetível (o
usuário provavelmente vai pedir de novo no futuro), perguntar:

> "Isso pode virar uma skill pra próxima vez. Quer que eu crie?"

Não perguntar pra tarefas pontuais ou perguntas simples. Só quando o
padrão de repetição for claro.

---

## Aprender com correções

Quando o usuário corrigir algo, melhorar uma resposta ou dar uma
instrução que parece permanente (frases como "na verdade é assim", "não
faça mais isso", "prefiro assim", "sempre que...", "evita...", "da
próxima vez..."), perguntar:

> "Quer que eu salve isso pra não precisar repetir?"

Se sim, identificar onde faz mais sentido salvar:

- **Sobre o negócio** (clientes, serviços, mercado) → `_memoria/empresa.md`
- **Sobre preferências e estilo** (tom de voz, formato, o que evitar) → `_memoria/preferencias.md`
- **Sobre prioridades e foco** (projetos, metas, prazos) → `_memoria/estrategia.md`
- **Regra de comportamento nessa pasta** → próprio `CLAUDE.md`

Salvar com uma linha nova clara, sem reformatar o arquivo inteiro.
Confirmar mostrando a linha adicionada.

Não perguntar se a correção for óbvia de contexto imediato (ex: "na
verdade o arquivo se chama X"). Só perguntar quando a informação tiver
valor duradouro.

---

## Manter contexto atualizado

Ao terminar uma tarefa que mudou algo relevante (cliente novo, skill
nova, mudança de foco, processo novo, ferramenta instalada, estrutura
alterada), perguntar:

> "Isso mudou algo no teu contexto. Quer que eu atualize a memória?"

Se sim, identificar o que atualizar:

- **Cliente, serviço, ferramenta, equipe** → `_memoria/empresa.md`
- **Mudança de prioridade ou foco** → `_memoria/estrategia.md`
- **Tom ou estilo** → `_memoria/preferencias.md`
- **Pasta, regra de organização, skill criada** → `CLAUDE.md`
- **Visual (cores, fontes, logo)** → `identidade/design-guide.md`

Mostrar o que vai mudar antes de salvar. Não reformatar o arquivo
inteiro, só adicionar ou editar a linha relevante.

**Quando NÃO perguntar:**
- Tarefas pontuais sem impacto no contexto (escrever um email avulso, criar um post)
- Perguntas simples ou conversas sem ação
- Mudanças já salvas pelo bloco "Aprender com correções"

**Dica:** rode `/atualizar` pra uma varredura completa quando houver dúvida.

---

## Criação de skills

Quando o usuário pedir skill nova:

1. Verificar se existe template relevante em `templates/skills/`. Se
   existir, usar como base e adaptar pro contexto
2. Perguntar se é específica desse projeto ou útil em qualquer:
   - Específica → `.claude/skills/nome-da-skill/SKILL.md` (local)
   - Universal → `~/.claude/skills/nome-da-skill/SKILL.md` (global)
3. Ler `_memoria/empresa.md` e `_memoria/preferencias.md` pra calibrar
   o conteúdo da skill ao contexto do negócio
4. Se a skill precisar de arquivos de apoio (templates, exemplos),
   criar dentro da pasta da skill
5. Seguir o fluxo da skill-creator nativa do Claude Code

---

# Vitamee — regras do negócio

> Bloco adicionado pelo `/instalar`. Perfil: **empresa**.

## O que é esse workspace
Operação da Vitamee — marca de suplementos (gummies e gotas). Aqui mora a
memória, a identidade e tudo que o sistema produz pra marketing, site, vendas
e operação.

## Sobre a empresa
Vitamee é uma marca de nutracêuticos em fase de validação. Sócios: **Luan**
(Economia, estratégia e execução) e **Natália**. Tese: suplementos de
qualidade com sabor e palatabilidade — "Vitamina para sua melhor versão!".
Linha principal em gummies, fabricação parceira. Detalhes em
`_memoria/empresa.md`.

## Setores / frentes ativas
- **Marketing & conteúdo:** Instagram (@vitamee), futuramente TikTok Shop com UGC
- **Site:** vitamee.br (layout pronto, em implementação)
- **Produto:** mineração de catálogo (demanda × margem), fichas e precificação
- **Comercial:** site próprio + planejamento de marketplaces/TikTok Shop

## Tom de voz
Amigável, profissional, cordial e despojado. Cria comunidade, gera conexão,
**sem falsas promessas**. Detalhes em `_memoria/preferencias.md`.

## Estrutura de pastas (descritiva — padrão MazyOS)
- `_memoria/` — empresa, preferências, estratégia (o Claude lê antes de cada resposta)
- `identidade/` — design-guide + logo + `referencias/` (manual de marca e keyvisual da Vitamee)
- `produtos/` — catálogo, fichas técnicas, precificação
- `marketing/` — conteúdo; subpastas `instagram/` e `trafego-pago/`
- `site/` — site vitamee.br
- `vendas/` — funil, scripts, pós-venda
- `financeiro/` — custos, fluxo, metas
- `dados/` — CSVs/planilhas pra análise (ex: tabela de fornecedores)
- `saidas/` — documentos pontuais
- `agentes/` — prompts/conhecimento dos agentes Vitamee (complementam as skills)
- `templates/` — modelos do MazyOS
- `_referencias/bull/` — material da Bull (outro negócio do Luan) usado só como referência/modelo. **Não é operação da Vitamee.**
- `.claude/skills/` — as 15 skills do MazyOS

## Regras do sistema
- Toda peça visual respeita `identidade/design-guide.md` (carvão + verde vital + branco; o sorriso verde é sagrado)
- Saídas de conteúdo vão pra `marketing/`; documentos pontuais pra `saidas/`
- Tabelas/CSVs de produtos e fornecedores entram em `dados/`
- Conteúdo da Bull é **referência**, fica em `_referencias/bull/` — nunca misturar com a operação da Vitamee
- Cuidado regulatório: nada de promessa terapêutica ou milagrosa (ANVISA)

## Pendências de setup
- [x] Logo ligado em `identidade/logo.png` (variações no manual de marca)
- [ ] Versão do logo pra fundo escuro / circular em `identidade/` (extrair do manual quando precisar)
- [ ] Receber tabela de produtos + fornecedores do Luan pra mineração (demanda × margem)
