---
tags:
  - #ICU_Pulse_Oximeter/planejamento
---
# Planejamento: Infográfico de Oximetria de Pulso (ICU One Pager)

## Objetivo
Traduzir e redesenhar do zero o infográfico "Pulse Oximetry" (Nick Mark MD) construindo um layout limpo e vetorial no LaTeX. O arquivo gerado será um pôster de altíssima qualidade contendo a teoria e a análise de ondas da oximetria.

## Escopo e Estrutura do Layout (LaTeX/TikZ)
O espaço do canvas será configurado para **A3 Paisagem (Landscape)** para garantir que o excesso de informações, ilustrações de ondas e gráficos caibam confortavelmente sem ficarem minúsculos.

### 1. Cabeçalho e Princípio (Topo)
- **Título**: Oximetria de Pulso (Pulse Oximetry).
- **Caixas de Fluxo**: Sequência de 4 caixas conectadas com setas explicando o princípio de absorção de luz vermelha e infravermelha.
- **Gráficos**:
  - Curva de Absorção vs Comprimento de Onda (OxyHb vs DeoxyHb).
  - Razão de Modulação (R) x SaO2 (%).
- **Desenho Esquemático**: Dedo com Diodo Emissor (Red/IR LED) e Fotodiodo (Photodiode), estilizado em TikZ.

### 2. Painel Central (Monitor)
- Tela representativa de ECG e onda plestimográfica com indicação do PTT (Pulse Transit Time).
- Valores lógicos de SpO2 (96) e HR (85).

### 3. Texto Explicativo em Grade (Precisão da Oximetria)
Grade de blocos informativos sobre causas de imprecisão:
- Tipo e Posicionamento do Sensor.
- Cor da Pele e Esmalte de Unhas.
- Estados de Baixo Fluxo.
- Hemoglobinas Anormais (MetaHb, CoHb).
- Menor Precisão em Baixa SpO2.
- Tempo de Atraso (Lag Time) e Efeitos de Medicações.

### 4. Análise de Onda Pletismográfica (Direita)
- Onda Base: Pico Sistólico, Pico Diastólico e incisura.
- Variações: Normal, Sinal Fraco, Vasoconstrição, Vasodilatação, Pulso Venoso. (Feito via `\draw plot` ou `\draw [out=..., in=...]`).

## Decisões Estéticas
- Fontes modernas e tipografia legível (`lmodern`).
- Abordagem em **Grid Absoluto** com coordenadas fixas para alinhamento simétrico impecável (já provado eficiente no PALS).
- Paleta de Cores: Azul Escuro (OxyHb/Ondas), Vermelho (Luz Visível/LED), Cinza Neutro (Fundos de caixas e bordas) e Laranja (Infravermelho).

## Avaliação do Usuário
A estrutura exigirá forte proficiência em renderização gráfica matemática do TikZ.
A página será programada no novo repositório `ICU_Pulse_Oximeter/Pulse_Oximetry.tex`.
