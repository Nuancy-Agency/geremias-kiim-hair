---
name: GKiim Hair — Geremias Kiim
description: Atelier editorial de um colorista independente em Lisboa — capa de revista, não landing page de salão.
colors:
  caramelo-dourado: "#C9975C"
  vinho-profundo: "#5B2333"
  bege-neutro: "#D8D6D2"
  preto-retrato: "#1A1A1A"
  papel: "#FDFCFB"
  marfim-nota: "#FFFDFA"
typography:
  display:
    fontFamily: "Playfair Display, ui-serif, Georgia, serif"
    fontSize: "clamp(2.75rem, 11vw, 4.25rem)"
    fontWeight: 400
    lineHeight: 0.95
    letterSpacing: "normal"
  headline:
    fontFamily: "Playfair Display, ui-serif, Georgia, serif"
    fontSize: "clamp(1.875rem, 4vw, 3rem)"
    fontWeight: 400
    lineHeight: 1.1
  body:
    fontFamily: "Inter, ui-sans-serif, system-ui, sans-serif"
    fontSize: "1rem"
    fontWeight: 400
    lineHeight: 1.6
  label:
    fontFamily: "Inter, ui-sans-serif, system-ui, sans-serif"
    fontSize: "0.75rem"
    fontWeight: 500
    letterSpacing: "0.15em"
rounded:
  full: "9999px"
  lg: "0.5rem"
  xl: "0.75rem"
  2xl: "1rem"
spacing:
  container: "72rem"
  gutter: "1.25rem"
  section-y: "5rem"
  section-y-lg: "7rem"
components:
  button-primary:
    backgroundColor: "{colors.vinho-profundo}"
    textColor: "#FFFFFF"
    rounded: "{rounded.full}"
    padding: "0.875rem 1.75rem"
  button-primary-hover:
    backgroundColor: "{colors.vinho-profundo}"
    textColor: "#FFFFFF"
  button-ghost:
    backgroundColor: "transparent"
    textColor: "#FFFFFF"
    rounded: "{rounded.full}"
    padding: "0.875rem 1.75rem"
---

# Design System: GKiim Hair — Geremias Kiim

## Overview

**Creative North Star: "O Atelier Editorial"**

O site é a capa de uma revista de moda, não o folheto de um salão de bairro: foto de estúdio em tela cheia, tipografia serifada enorme, e uma grade disciplinada que organiza tudo com a mesma precisão de um layout Swiss. A voz é boutique, técnica e pessoal — nunca genérica de "salão de beleza". A confiança vem da fotografia real e do texto editorial, não de selos, badges ou grades de cards decorativos.

O sistema rejeita explicitamente o padrão anterior do mesmo projeto — "card + pill + soft-shadow aplicado a toda seção" — como visual genérico. Neste build, sombra suave e elevação são reservadas a elementos tocáveis (cartões de depoimento, itens de galeria, botões), nunca aplicadas como decoração de bloco estrutural ou de fotografia full-bleed.

Um glifo assinatura (✳) substitui um logo convencional — recorrente no header, hero, Essência, CTA final e rodapé — reforçando o caráter pessoal e assinado do trabalho de Geremias.

**Key Characteristics:**
- Hero editorial em tela cheia (foto grande + Playfair Display gigante sobre fundo quase-preto).
- Grade de duas colunas assimétrica (proporções tipo 0.9fr/1.1fr, 1.1fr/1fr) em quase toda seção.
- Sombra suave e `hover-lift` (translateY -4px, 200-300ms) só em elementos tocáveis; nunca em blocos estruturais.
- Numeração editorial (01, 02, 03...) como dispositivo de lista recorrente, no lugar de bullets ou ícones.
- Glifo assinatura ✳ como marca pessoal recorrente, no lugar de um logotipo genérico.

## Colors

Paleta quente e restrita: dourado/caramelo como acento raro, vinho profundo reservado à ação (CTA), preto quase puro e bege neutro como base.

### Primary
- **Caramelo Dourado** (#C9975C): acento — links em hover, glifo assinatura, números de índice, losango do divisor ornamental, primeira letra em drop-cap. Nunca usado como cor de fundo de bloco grande.

### Secondary
- **Vinho Profundo** (#5B2333): cor de ação — todo botão primário/CTA ("Peça seu orçamento", "Agendar"), fundo da seção de CTA final, link de skip-link. É a única cor usada para convidar ao clique.

### Neutral
- **Preto Retrato** (#1A1A1A): texto de corpo padrão; também fundo do hero e do rodapé (duplo papel: cor de texto em seções claras, cor de fundo em seções de contraste total).
- **Bege Neutro** (#D8D6D2): fundo alternado de seções pares (Técnica, Depoimentos), sempre a ~40% de opacidade sobre o papel base — nunca sólido.
- **Papel** (#FDFCFB): fundo padrão do body e do header — quase-branco quente, não branco puro.
- **Marfim Nota** (#FFFDFA): fundo dos cartões "nota pessoal" (mosaico da Essência), quase indistinguível do papel mas levemente mais claro para destacar a textura de post-it.

### Named Rules
**The Rare Accent Rule.** Caramelo Dourado nunca preenche um bloco grande — é traço, número, glifo ou hover, nunca superfície.
**The One Action Color Rule.** Vinho Profundo é a única cor usada em botões de ação. Se um botão não leva ao WhatsApp/ação primária, ele não usa essa cor.

## Typography

**Display Font:** Playfair Display (com ui-serif, Georgia, serif de fallback)
**Body Font:** Inter (com ui-sans-serif, system-ui, sans-serif de fallback)

**Character:** Serifada editorial de revista (Playfair) contra sans neutra e legível (Inter) — a mesma dupla usada em todo título e todo corpo do site, sem terceira família.

### Hierarchy
- **Display** (peso 400, `clamp(2.75rem, 11vw, 4.25rem)` até `text-8xl` em telas largas, leading 0.95): título do hero, exclusivo da primeira dobra.
- **Headline** (peso 400, `text-3xl` a `text-5xl` conforme breakpoint, leading ~1.1): H2 de cada seção (Essência, Técnica, Cardápio, Galeria, Depoimentos, O espaço) — escala idêntica em toda seção, sem exceção. Os nomes de tom no Cardápio (`<h3>`) também usam essa escala: cada transformação é tratada como um momento de peso Headline, não um Title menor.
- **Title** (peso 400, `text-xl`/`text-2xl`): itens numerados da Técnica, citações longas em Depoimentos.
- **Body** (peso 400, `text-base`/`text-lg`, texto a 65–75% de opacidade sobre `preto-retrato`): parágrafos de corpo em Inter.
- **Label** (peso 500, `text-xs`, `letter-spacing: 0.15em`, uppercase): legendas de índice do hero, tagline do header, créditos do rodapé, legendas de galeria em hover.

### Named Rules
**The Two-Family Rule.** Apenas Playfair Display (títulos/números editoriais) e Inter (corpo/labels). Nenhuma terceira família, nunca uma fonte display de sistema.

## Layout

Contêiner central `max-w-6xl` (72rem/1152px) com gutter lateral `px-5` (20px), exceto o hero e o rodapé/CTA que ocupam a largura total da viewport. Ritmo vertical de seção consistente: `py-20` (80px) em mobile, `py-28` (112px) em `md:`. A maioria das seções usa grade de duas colunas assimétrica (`0.9fr/1.1fr`, `0.8fr/1.2fr`, `1.1fr/1fr` no hero), com uma coluna de texto `sticky` acompanhando o scroll ao lado do conteúdo visual. O Cardápio de tons alterna a ordem imagem/texto a cada item (`lg:order-2`) para criar ritmo de zig-zag editorial. Header é `sticky top-0` com fundo semitransparente e `backdrop-blur`.

## Elevation & Depth

O sistema é majoritariamente plano: fotografia full-bleed, blocos estruturais e o hero/rodapé de fundo escuro não recebem sombra. Sombra é reservada, difusa e sempre com deslocamento negativo generoso (nunca "hard offset"), aplicada só a elementos tocáveis ou a imagens em cartão: cartões de depoimento, itens da galeria, blocos de imagem da Essência, cartões "nota pessoal", e o mapa incorporado. `hover-lift` (translateY -4px, scale 1.01, 250ms `cubic-bezier(0.16,1,0.3,1)`) é a única resposta de interação — nunca aplicada a blocos estruturais ou fotografia de capa.

### Shadow Vocabulary
- **Ambient Card** (`box-shadow: 0 10px 30px -18px rgba(26,26,26,0.35)`): cartões de imagem da Essência, cartões de depoimento, mapa incorporado.
- **Ambient Gallery** (`box-shadow: 0 8px 24px -16px rgba(26,26,26,0.4)`): itens da galeria de portfólio.
- **Note Shadow** (`box-shadow: 0 10px 24px -18px rgba(26,26,26,0.35)`): cartões "nota pessoal".

### Named Rules
**The Touch-Only Elevation Rule.** Sombra aparece só em elementos com estado de hover/interação real. Fotografia de capa, hero e blocos estruturais permanecem planos.

## Shapes

Botões e pílulas de ação usam raio total (`rounded-full`, 9999px) — CTA principal, CTA secundário, botão de WhatsApp, toggle de menu mobile. Cartões de imagem e conteúdo usam raio médio (`rounded-2xl`, 16px) ou pequeno (`rounded-xl`, 12px). A lista numerada de serviços (Técnica) é a exceção deliberada: sem raio, delimitada por `border-t`/`border-b` finas e divisores horizontais — um tratamento de índice editorial, não de cartão. O divisor ornamental (`.divider-gold`) é o único elemento geométrico decorativo recorrente: duas linhas finas ladeando um losango dourado de 6px rotacionado 45°.

## Components

### Buttons
- **Shape:** pílula total (`rounded-full`, 9999px), altura mínima 44px (`min-h-11`).
- **Primary:** fundo Vinho Profundo (#5B2333), texto branco, padding `0.875rem 1.75rem` (`px-7 py-3.5`) — todo CTA de agendamento/orçamento.
- **Hover / Focus:** `hover-lift` (translateY -4px, scale 1.01, 250ms) em hover; anel de foco visível 2px na cor Vinho Profundo com `outline-offset: 2px` em teclado (`:focus-visible`), nunca removido.
- **Ghost (sobre hero escuro):** borda `border-white/25`, fundo transparente, texto branco — usado só sobre o fundo #1A1A1A do hero.
- **Ghost outline (Cardápio):** pílula com borda Vinho Profundo 1px, texto Vinho Profundo, fundo transparente; preenche com Vinho Profundo sólido e texto branco no hover — usado só no Cardápio de tons, onde a foto grande já carrega o peso visual principal e o CTA precisa de presença sem competir com ela.

### Cards / Containers
- **Corner Style:** `rounded-2xl` (16px) para cartões de depoimento e blocos de imagem; `rounded-xl` (12px) para itens de galeria e notas pessoais.
- **Background:** branco puro para cartões de depoimento; Marfim Nota (#FFFDFA) para notas pessoais; imagem crua para itens de galeria.
- **Shadow Strategy:** ver Elevation & Depth — Ambient Card / Ambient Gallery / Note Shadow conforme o tipo.
- **Border:** notas pessoais usam borda tracejada 1px em Caramelo Dourado a 55% de opacidade (estilo post-it); cartões de depoimento usam borda sólida 1px `black/5`.
- **Internal Padding:** `p-5` a `p-6` conforme o cartão.

### Navigation
- Header fixo (`sticky top-0`) com fundo `papel` a 90% de opacidade e `backdrop-blur`. Links de texto em Inter, estado hover muda a cor para Caramelo Dourado com sublinhado animado (`.nav-link`, cresce da esquerda, 300ms). Menu mobile é um painel deslizante com os mesmos links empilhados e o CTA de WhatsApp em destaque.

### Cartões de Depoimento
Grade `columns-*` (mesma mecânica de masonry da Galeria), nunca fita horizontal — o cliente precisa ver os depoimentos no fluxo normal de rolagem vertical da página, sem precisar de uma interação separada. Reveal escalonado por card (`--reveal-delay`) e leve inclinação alternada (`-rotate-1`/`rotate-1`) dão o toque dinâmico. Fonte e tamanho idênticos em todos os cartões (`font-display text-xl sm:text-2xl`) — sem variação de peso entre eles.

### Glifo Assinatura (componente de assinatura)
O caractere ✳ em Playfair Display substitui um logotipo convencional — aparece no header (dentro de um círculo com borda dourada), no hero, na Essência, no CTA final e no rodapé. É a única marca gráfica recorrente do sistema; não é um ícone de UI funcional, é uma assinatura pessoal do colorista.

## Do's and Don'ts

### Do:
- **Do** reservar sombra e `hover-lift` a elementos com interação real (cartões, botões, itens de galeria) — nunca a blocos estruturais ou à fotografia de capa.
- **Do** manter Vinho Profundo (#5B2333) exclusivo aos botões de ação; nenhuma outra cor de botão de CTA.
- **Do** usar numeração editorial (`01`, `02`...) em Playfair Display translúcido como dispositivo de lista, no lugar de bullets ou ícones genéricos.
- **Do** manter o glifo ✳ como única marca gráfica recorrente do site.

### Don't:
- **Don't** preencher blocos grandes com Caramelo Dourado — é acento, nunca superfície.
- **Don't** introduzir uma terceira família tipográfica ou uma fonte display de sistema.
- **Don't** voltar ao padrão "card + pill + soft-shadow em toda seção" — é o visual genérico já rejeitado nesta reconstrução.
- **Don't** usar sombra com deslocamento duro ("hard offset shadow") — toda sombra do sistema é difusa e ambiente.
