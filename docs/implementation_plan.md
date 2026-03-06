# Plano de Implementação: PALS 2025 Algoritmo Profissional

O objetivo é transformar o algoritmo anterior em um documento de qualidade tipográfica e de design de informação muito superior, digno de ser impresso profissionalmente como *card* de bolso ou pendurado em um carrinho de emergência.

## User Review Required

> [!IMPORTANT]
> **Formato Físico (A4 vs Card de Bolso):** 
> O algoritmo completo do PALS tem muitas caixas. Tentá-lo colocar em um formato de crachá (ex: 9x6cm) deixaria o texto microscópico. 
> Minha proposta é desenhá-lo primorosamente para **A4 Paisagem (Landscape)**, que é o padrão da AHA para carrinhos de parada (Crash Carts), com a possibilidade de ser impresso reduzido (ex: formato A5 ou dobrável de bolso). O novo design será completamente vetorial e escalável, sem perda de qualidade.
>
> **Você concorda em mantermos o canvas como A4 Paisagem super otimizado e elegante, ou prefere estritamente as dimensões físicas de um folheto/card específico (ex: 15x20cm)?**

## Proposed Changes

### 1. Tipografia Moderna e Elegante
Substituiremos a fonte padrão feia por uma tipografia sem serifa moderna, limpa e altamente legível para uso médico:
- Utilizaremos a fonte **Latin Modern Sans** (`lmodern`) ou **Fira Sans** / **Roboto** (se disponível na sua distribuição). Como garantia de não quebrar a compilação no TeX Live básico, usaremos uma configuração segura que invoca a fonte vetorizada correta e limpa.
- Textos justificados ou perfeitamente alinhados à esquerda (raggedright) dentro dos nós, sem hifenizações quebras estranhas.

### 2. Design de Caixas e "Alma"
- Adição de sombras projetadas muito suaves e elegantes usando `\usetikzlibrary{shadows.blur}`.
- Refinamento das paletas de cores usando tons pastéis no fundo (gradientes sutis) e bordas finas com cores da AHA (Vermelho AHA, Amarelo AHA, Azul Claro AHA, Verde AHA).
- Tamanho unificado dos nós (*nodes*) sempre que possível para criar harmonia visual (ex: mesma largura de caixas laterais).

### 3. Setas e Espaçamentos (Routing)
- Utilizaremos setas com cabeças modernas (biblioteca `arrows.meta`, tipo `-Latex` grossas).
- O espaçamento (`node distance`) será ampliado vertical e horizontalmente para criar respiro (White Space) e guiar o olho.
- Junções e ramificações usando caminhos ortogonais retos (`|-` e `-|`) matematicamente calculados, removendo a desconfiguração visual.

### 4. Layout
O layout consistirá do tronco principal sendo bifurcado perfeitamente no centro para "Ritmos Chocáveis" (esquerda) e "Assistolia/AESP" (direita), enquanto os blocos de texto auxiliares (Medicamentos, Via aérea, etc.) ficarão em uma bela barra lateral bem alinhada.

## Verification Plan

### Teste de Compilação
- Compilaremos rodando `pdflatex -interaction=nonstopmode PALS_CA_2025_v2.tex`.
- Validaremos se o output log não possui erros de caractere (`Missing character`).

### Verificação Manual
- Abriremos o PDF compilado para inspecionar rigorosamente o fluxo das linhas (sem sobreposições) e a pureza do design. Mostrar o PDF gerado ao final ao usuário.
