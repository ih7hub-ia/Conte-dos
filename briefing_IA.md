# Briefing diário de IA automático

Passo a passo para ter um briefing de notícias de IA pronto todo dia, usando a skill deste repositório e uma rotina agendada no Claude ou no ChatGPT. No final, veja como receber o briefing por e-mail ou Telegram usando o Zapier.

---

## O que você precisa

- A **skill do briefing** (o arquivo `SKILL.md` deste repositório, logo abaixo)
- Uma conta no **Claude** (Cowork ou Claude Code) **ou** no **ChatGPT** (ChatGPT ou Codex) - versão paga
- Opcional: uma conta no **Zapier**, para enviar o briefing por e-mail ou Telegram - versão gratuita

---

## Opção 1: Claude

### 1. Instale a skill

**No Claude (app, Cowork):**

1. Baixe a pasta da skill e compacte em `.zip` (a pasta precisa conter o `SKILL.md`).
2. Vá em **Configurações → Capacidades → Skills**.
3. Clique em **Enviar skill** e selecione o `.zip`.
4. Confira se a skill aparece ativada na lista.

**No Claude Code:**

1. Copie a pasta da skill para `~/.claude/skills/briefing-ia/` (para usar em todos os projetos) ou para `.claude/skills/briefing-ia/` dentro do projeto.
2. Abra o Claude Code e peça: *"Monta o briefing de IA de hoje"* para testar.

### 2. Teste antes de agendar

Numa conversa nova, peça:

> Monta o briefing de IA das últimas 24h usando a skill de briefing.

Ajuste a skill se o formato ou as fontes não estiverem como você quer.

### 3. Crie a rotina

**No Cowork:** peça em uma conversa:

> Cria uma tarefa agendada de segunda a sexta às 7h40 que monta o briefing de IA das últimas 24h usando a skill de briefing.

O Claude cria a tarefa e ela aparece na lista de tarefas agendadas, onde você pode pausar, editar ou rodar na hora.

**No Claude Code:** use as rotinas agendadas (ex.: comando `/schedule`) com o mesmo pedido acima.

---

## Opção 2: ChatGPT

### 1. Instale a skill

**No ChatGPT:** crie um **Projeto** (ou um GPT personalizado) chamado "Briefing IA" e cole o conteúdo do `SKILL.md` nas **instruções**. Se a sua conta tiver a área de Skills, envie o arquivo por lá.

**No Codex:** coloque a pasta da skill no diretório de skills do Codex (ex.: `~/.codex/skills/briefing-ia/`) ou cole o conteúdo no `AGENTS.md` do projeto.

### 2. Teste antes de agendar

> Monta o briefing de IA das últimas 24h seguindo as instruções da skill de briefing.

### 3. Crie a rotina

No ChatGPT, peça:

> Todo dia útil às 7h40, monte o briefing de IA das últimas 24h seguindo as instruções deste projeto.

O ChatGPT cria uma **Tarefa agendada** e avisa quando o briefing fica pronto. As tarefas ficam no menu **Tarefas**, onde dá para editar ou pausar.

> Os nomes dos menus mudam com frequência nas duas plataformas. Se não achar algum botão, pergunte ao próprio assistente: "onde instalo uma skill?" ou "como crio uma tarefa agendada?".

---

## Bônus: receber por e-mail ou Telegram com o Zapier (MCP)

### 1. Configure o Zapier MCP

1. Acesse **mcp.zapier.com** e crie um servidor MCP.
2. Adicione as ações que vai usar:
   - **Gmail → Send Email** (para e-mail)
   - **Telegram Bot → Send Message** (para Telegram)
3. Conecte suas contas quando o Zapier pedir.
4. Copie a **URL do servidor MCP**.

**Para o Telegram:** crie um bot no **@BotFather** (comando `/newbot`), guarde o token, conecte no Zapier e mande uma mensagem para o bot para ele encontrar o seu chat.

### 2. Conecte o Zapier ao assistente

- **Claude:** **Configurações → Conectores → Adicionar conector personalizado** e cole a URL do Zapier.
- **ChatGPT:** **Configurações → Apps/Conectores**, adicione um conector personalizado com a URL do Zapier (pode exigir ativar o modo desenvolvedor).

### 3. Inclua o envio na rotina

Edite o pedido da rotina para terminar com o envio:

> Monte o briefing de IA das últimas 24h usando a skill de briefing e **envie pelo Zapier** por e-mail para seuemail@exemplo.com com o assunto "Briefing IA – [data]".

ou

> ... e **envie pelo Zapier** como mensagem no meu Telegram.

Pronto: todo dia o briefing chega na sua caixa de entrada ou no Telegram.





---
name: briefing-ia-diario (SKILL)
description: "Monta o briefing matinal de notícias de IA das últimas 24-48h, com recorte de estratégia e negócio, fontes de autoridade verificadas e o \"so what\" de cada item. Use quando a Jeni pedir briefing, resumo do dia, o que rolou em IA, ou novidades."
---

# Briefing diário de IA

Briefing matinal para a Jeni (Jenifer Calvi), estrategista de IA para negócios — IH7.
Entregue como **texto na conversa**, em português do Brasil. Não crie arquivo nem publique página, a menos que ela peça.

## Recorte

**Estratégia e negócio.** Priorize o que muda decisão de empresa: movimento de big tech, preço, adoção, contrato, regulação, funding relevante. Notícia técnica entra apenas quando tem consequência prática — benchmark só importa se muda escolha de fornecedor ou de arquitetura.

**Janela:** últimas 24 a 48 horas.

## Método (obrigatório)

1. **Quatro ângulos, uma busca cada:**
   - lançamento de modelo e produto
   - movimento de big tech — OpenAI, Anthropic, Google, Meta, Microsoft, xAI, Nvidia
   - regulação e política
   - mercado, funding e adoção enterprise
2. **Leia a página completa com WebFetch antes de escrever qualquer item.** Nunca escreva a partir do snippet de busca.
3. **Hierarquia de fontes:**
   - Lançamento e preço → blog oficial do lab (openai.com/news, anthropic.com/news, deepmind.google/discover/blog)
   - Regulação → fonte oficial (Comissão Europeia, DOU, agência reguladora)
   - Mercado e negócio → Reuters, Bloomberg, Financial Times, The Information, MIT Technology Review, The Verge, TechCrunch, Wired; Gartner e McKinsey quando houver
4. **Duas fontes para notícia de mercado.** Se só houver uma, marque como fonte única.
5. **Descarte:** rumor não confirmado, clickbait, agregador sem apuração própria, post promocional, "publi" disfarçada de análise.
6. **Nunca invente número, data ou citação.** Se as fontes divergirem, diga qual é a divergência — isso é informação útil, não falha.
7. **Etiquete o status de cada item:**
   - `[confirmado]` — fonte oficial ou duas independentes
   - `[reportado]` — uma fonte de autoridade, sem confirmação oficial
   - Regulatório: `[vigente]` `[proposta]` `[aprovado]` `[em consulta]`

## Formato de saída

```
Briefing IA · [data por extenso]
[uma linha: a leitura do dia — o que realmente importa nas últimas 24-48h]

### [Título curto, máx. 8 palavras]
[2 a 3 frases com o fato, número e data]
**So what:** [consequência estratégica concreta para quem vende, implementa ou decide sobre IA em empresa]
[Fonte](link) · `[status]`
```

De **5 a 8 notícias**. Depois:

**Radar de negócios** — 2 a 3 movimentos relevantes para estratégia e go-to-market, cada um em duas ou três frases, ligando o fato à ação comercial.

**Fora do radar hoje** — uma linha com o que apareceu muito e foi descartado, e por quê. Esse bloco é o que prova que houve filtro.

## Tom

Direto, de analista. Sem adjetivo de hype — nada de "revolucionário", "game changer", "impressionante". Respeite o tempo de quem lê.

**Se o dia foi fraco, diga isso e entregue 4 itens.** Inventar volume é pior que entregar pouco — e um dia fraco também é informação.

## Fontes de referência

A lista completa de fontes por camada (labs, pessoas de dentro, investidores, aplicação, destiladores) está no documento `claude/fontes-ia-referencia.md` do projeto "Produção de conteúdo". Consulte quando precisar ampliar a cobertura de um ângulo.
