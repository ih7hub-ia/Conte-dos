---
name: briefing-ia-diario
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
