# Eleições 2026 — Web scraping, estatística e painel interativo

[![Abrir no Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/beatriztrajano/webscrapping_eleicoes2026/blob/main/eleicoes_2026_webscraping.ipynb)

Projeto acadêmico de ciência de dados com os resultados das **Eleições 2026** (Presidente e Governador, 1º e 2º turno), feito em Python no Google Colab.

## O que o projeto faz

| Parte | Descrição | Fonte |
|---|---|---|
| **A** | Coleta os JSONs oficiais do TSE (1º turno), gera CSVs, gráficos e estatísticas: mediana, desvio padrão, IQR, moda, correlação de Spearman, padronização e PCA | resultados.tse.jus.br |
| **B** | Painel interativo com mapa municipal fixo do Brasil, Top 5 de candidatos, cores por partido e comparação entre turnos | Votação por seção e cadastro de candidaturas (TSE) + malha municipal (IBGE, via `geobr`) |

## Como executar

1. Clique no botão **Abrir no Colab** acima.
2. Use **Ambiente de execução → Executar tudo**.
3. A primeira execução baixa arquivos grandes do TSE; as seguintes usam o cache.

Para testar mais rápido, reduza `UFS_GOVERNADOR` na seção B2 do notebook.

## Estrutura

```
.
├── eleicoes_2026_webscraping.ipynb      # notebook completo (Partes A e B)
├── requirements.txt  # dependências (o Colab já traz a maioria)
├── resultados/       # CSVs e gráficos gerados pela Parte A
└── README.md
```

## Observações

- Os arquivos brutos do TSE (ZIPs) e o cache não são versionados (ver `.gitignore`).
- As requisições à fonte são sequenciais e com pausa, para não sobrecarregar os servidores do TSE.
- As cores do mapa são categorias visuais por sigla partidária, não a identidade oficial dos partidos.
- Percentuais do painel consideram apenas votos atribuídos a candidaturas (sem brancos e nulos).

## Fontes dos dados

- Tribunal Superior Eleitoral (TSE) — resultados e dados abertos.
- IBGE — malha municipal 2022.
