# metep-trabalho-final

Baseline de k-anonimato (Basic Mondrian) sobre dados do SiSU, com modelação de ataques de inferência.

## Estrutura

```
experimental_base/   → CSVs do SiSU 2016 (T1: 1ª Chamada, T2: 2ª Chamada)
Basic_Mondrian/      → Implementação do algoritmo Mondrian (Python 2, original)
baseline_mondrian_metep.ipynb  → Notebook principal (Python 3)
```

## Como executar

Abra e execute o notebook `baseline_mondrian_metep.ipynb` num ambiente com `pandas`, `numpy`, `matplotlib` e `seaborn`.

Os arquivos CSV do SiSU 2016 são **baixados automaticamente** na Secção 1 do notebook, caso não estejam presentes em `experimental_base/`. O download usa apenas a stdlib do Python (`urllib`, `html.parser`) — sem dependências adicionais. Se o portal estiver indisponível, a célula imprime o URL para download manual.

## Tamanho da amostra

Por padrão o notebook usa as primeiras **1.000 linhas** de cada arquivo. Ajuste a constante `NROWS` no topo do notebook conforme a necessidade:

| `NROWS` | Uso recomendado |
|---------|----------------|
| `1_000` | Testes rápidos (padrão) |
| `50_000` | Experimentos representativos |
| `None` | Todos os registros (~5,3M em T1, ~1,7M em T2) - requer ≥ 8 GB de RAM livre |

Para carregar todos os registros com pouca memória, use leitura em chunks (já documentado no notebook, Secção 1).
