# 📊 Data Science — VNL 2024

Análise exploratória dos dados da **Liga das Nações Feminina de Vôlei 2024 (VNL 2024)**, com o objetivo de identificar os fundamentos que mais contribuíram para o desempenho das seleções, ranquear as jogadoras mais eficientes e comparar os resultados estatísticos com os destaques oficiais divulgados pela FIVB.

> Projeto desenvolvido com vivência esportiva: a autora é atleta de vôlei e traz essa perspectiva para a interpretação dos dados.

---

## ❓ Perguntas Investigadas

- O que os dados revelam sobre o desempenho das seleções do pódio?
- Quais foram as jogadoras mais eficientes por fundamento?
- Ataque, bloqueio, saque, defesa e recepção — quais se destacaram mais?
- Como cada país performou em cada fundamento?
- Quais fundamentos tiveram maior aproveitamento para as seleções que subiram ao podium?
- As seleções mais eficientes são as que estão no top 3?
- Os dados confirmam a seleção oficial do campeonato?
- Como estão distribuídas as posições em quadra?
- Onde estão os países participantes? (mapa interativo)

---

## 📁 Estrutura do Projeto

```
Data-Science/
│
├── Notebook_final.ipynb                  # Análise completa com código, gráficos e conclusões
├── Relatorio_VNL_2024.md                 # Relatório narrativo da análise
├── Relatorio_VNL_2024.pdf                # Versão PDF do relatório (sem gráficos)
└── Relatorio_VNL_2024_com_graficos.pdf   # Versão PDF do relatório com visualizações
```

---

## 🗂️ Dataset

**Fonte:** [Kaggle — Volleyball Nations League Women 2024](https://www.kaggle.com/datasets/santibruno/volleyball-nations-league-women-2024)

Estatísticas individuais das jogadoras participantes da VNL 2024.

| Variável         | Descrição                                      |
|------------------|------------------------------------------------|
| `jogadora`       | Nome da jogadora                               |
| `pais`           | País da seleção                                |
| `posicao`        | Posição (líbero, oposta, ponteira, central...) |
| `ataque`         | Pontos de ataque                               |
| `bloqueio`       | Pontos de bloqueio                             |
| `saque`          | Pontos de saque                                |
| `defesa`         | Estatística defensiva                          |
| `recepcao`       | Estatística de recepção                        |
| `pontos_totais`  | Soma de pontos por jogadora                    |

---

## 🔧 Transformações Aplicadas

- Criação da coluna `jogadora_completa` (nome + posição + país)
- Tradução dos valores das posições para português
- Ranqueamento das **top 10 jogadoras** em pontuação geral
- Ranqueamento das **top 5 jogadoras** por fundamento
- Mapeamento geográfico dos países participantes com **Folium**
- Regressão linear para estimar desempenho por idade com **scikit-learn**

---

## 🤖 Modelo Desenvolvido

Regressão linear simples para estimar o impacto da idade no desempenho individual.

**Equação obtida:**

```
Pontos Totais = -0.06 × Idade + 5.88
```

O coeficiente negativo indica uma leve tendência de queda com o aumento da idade, mas o impacto é praticamente irrelevante (~0,06 pontos/ano). A conclusão é que **a idade sozinha não determina o desempenho** — posição, tempo de quadra e papel tático exercem influência muito maior.

---

## 🏆 Principais Conclusões

**O pódio (Itália 🥇, Japão 🥈, Polônia 🥉) é confirmado pelos dados:**

- **Itália** — desempenho mais equilibrado em todos os fundamentos
- **Japão** — liderou com folga os fundamentos defensivos (recepção e defesa)
- **Polônia** — destaque especial nos bloqueios

**Brasil** ficou em 4º lugar: apesar do alto aproveitamento em ataques e saques, o baixo desempenho defensivo comprometeu o resultado.


**Comparação com a seleção oficial da FIVB:** Egonu, Orro, Fahr e Korneluk aparecem em ambas as seleções. As diferenças ficaram nas ponteiras — os dados apontam Gabi Guimarães (BRA) e Inoue (JPN), enquanto a FIVB escolheu Sylla (ITA) e Koga (JPN), evidenciando que critérios qualitativos e táticos também pesam na escolha oficial.

---

## ⚙️ Tecnologias Utilizadas

| Biblioteca     | Uso                                         |
|----------------|---------------------------------------------|
| `pandas`       | Manipulação e transformação dos dados       |
| `matplotlib`   | Visualizações estáticas                     |
| `seaborn`      | Gráficos estatísticos                       |
| `folium`       | Mapa interativo dos países participantes    |
| `scikit-learn` | Regressão linear (idade × desempenho)       |

---

