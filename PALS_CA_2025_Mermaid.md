# Algoritmo de Parada Cardiorrespiratória Pediátrica (PALS 2025)

Esse arquivo apresenta o algoritmo principal do PALS renderizado através do Mermaid. Para visualizá-lo, você pode usar a preview do Obsidian, VS Code, Github, ou colar o código no site [Mermaid Live Editor](https://mermaid.live).

```mermaid
flowchart TD
    %% Nós principais e Roteamento
    title[**Algoritmo de Parada Cardiorrespiratória Pediátrica PALS 2025**] --- 1

    1["**1. Iniciar RCP**<br/>- Ventilação com bolsa-máscara e fornecer oxigênio<br/>- Instalar monitor/desfibrilador"]:::redBox --> shock1{"Ritmo<br/>chocável?"}

    %% ================= Lado Esquerdo =================
    shock1 -- Sim --> 2["**2. FV/TV sem pulso**"]:::redBox
    2 --> 3["**3. Choque**<br/>(o mais rápido possível)"]:::yellowBox
    3 --> 4["**4. RCP por 2 min**<br/>- Acesso IV/IO"]:::blueBox
    4 --> shock2{"Ritmo<br/>chocável?"}
    
    shock2 -- Sim --> 5["**5. Choque**"]:::yellowBox
    5 --> 6["**6. RCP por 2 min**<br/>- Epinefrina a cada 3 a 5 min<br/>- Considerar via aérea avançada e capnografia"]:::blueBox
    6 --> shock3{"Ritmo<br/>chocável?"}
    
    shock3 -- Sim --> 7["**7. Choque**"]:::yellowBox
    7 --> 8["**8. RCP por 2 min**<br/>- Amiodarona ou lidocaína<br/>- Tratar causas reversíveis"]:::blueBox
    8 --> shock_loop{"Ritmo<br/>chocável?"}
    shock_loop -- Sim --> 5
    
    %% ================= Lado Direito =================
    shock1 -- Não --> 9["**9. Assistolia/AESP**"]:::redBox
    9 --> 10pre["**Epinefrina**<br/>(o mais rápido possível)"]:::blueBox
    10pre --> 10["**10. RCP por 2 min**<br/>- Acesso IV/IO<br/>- Epinefrina a cada 3 a 5 min<br/>- Considerar via aérea avançada e capnografia"]:::blueBox
    10 --> shock4{"Ritmo<br/>chocável?"}
    
    shock4 -- Não --> 11["**11. RCP por 2 min**<br/>- Tratar causas reversíveis"]:::blueBox
    11 --> shock5{"Ritmo<br/>chocável?"}
    
    %% ================= Cruzamentos para a Esquerda =================
    shock4 -- Sim --> 5
    shock5 -- Sim --> 7
    shock5 -- Não --> 10
    
    %% ================= Saída (Caixa Verde) =================
    shock2 -- Não ----> 12
    shock3 -- Não ----> 12
    shock_loop -- Não ----> 12
    
    12["**12.**<br/>- Se não houver retorno da circulação espontânea (RCE), vá para 10 ou 11<br/>- Se houver RCE, vá para Cuidados Pós-Parada"]:::greenBox

    %% ================= Estilização AHA =================
    classDef redBox fill:#cd202c,color:#fff,stroke:#333,stroke-width:2px,border-radius:6px;
    classDef yellowBox fill:#f0ab00,color:#000,stroke:#333,stroke-width:2px,border-radius:6px;
    classDef blueBox fill:#006fb4,color:#fff,stroke:#333,stroke-width:2px,border-radius:6px;
    classDef greenBox fill:#008542,color:#fff,stroke:#333,stroke-width:2px,border-radius:6px;

    %% ================= Dicas Laterais Subgraph =================
    subgraph painel [Painel Auxiliar de Referência Rápida]
        direction TB
        side1["**Qualidade da RCP**<br/>- Força e rapidez (100 a 120/min), permitir retorno total.<br/>- Minimizar interrupções.<br/>- Alternar profissional a cada 2 min.<br/>- Sem via aérea: 15:2.<br/>- Com via aérea: contínua + 1 ventilação/2-3s."]:::grayBox
        side2["**Energia de Choque**<br/>- 1º: 2 J/kg<br/>- 2º: 4 J/kg<br/>- Subsequentes: ≥ 4 J/kg (Máx 10 J/kg ou dose adulto)"]:::grayBox
        side3["**Terapia Medicamentosa**<br/>- Epinefrina: 0,01 mg/kg IV/IO (Máx 1 mg).<br/>- Amiodarona: 5 mg/kg IV/IO (Máx 300 mg). Repetir até 3 doses. OU<br/>- Lidocaína: 1 mg/kg IV/IO."]:::grayBox
        side4["**Via Aérea Avançada**<br/>- Intubação endotraqueal ou supraglótica.<br/>- Capnografia para confirmação."]:::grayBox
        side5["**Causas Reversíveis (5Hs e 5Ts)**<br/>- Hipovolemia, Hipóxia, H+ (acidose), Hipoglicemia, Hipo/hipercalemia, Hipotermia.<br/>- Tensão (Pneumotórax), Tamponamento, Toxinas, Trombose pulm./coronária."]:::grayBox
    end
    
    classDef grayBox fill:#f4f4f4,color:#333,stroke:#ccc,stroke-width:1px,border-radius:4px,text-align:left;
```
