# Base de Conhecimento

## Dados Utilizados

> Descreva se usou os arquivos da pasta `data`, por exemplo:

| Arquivo | Formato | Utilização no Agente |
|---------|---------|---------------------|
| `entrada.csv` | CSV | Lista de entradas previstas por mês para uso na projeção de ganhos do usuário |
| `saidas.csv` | CSV | Lista de saídas previstas por mês para uso nas projeções dos usuários|
| `lista_de_desejos.csv` | CSV | Lista de desejos com valores previstos |

---

## Estratégia de Integração

### Como os dados são carregados?
> Há duas possibilidades, um arquivo atualizado pode ser upado e substituir a base atual ou o usuário pode solicitar via prompt adições e exclusões de registros da base de dado original. O chat sempre deve confirmar as alterações.

```python
import pandas as pd
entradas = pd.read_csv('data/entradas.csv')
saidas = pd.read_csv('data/saidas.csv')
lista = pd.read_csv('data/lista.csv')
```


### Como os dados são usados no prompt?
> Os dados vão no system prompt? São consultados dinamicamente?

```text
DADOS DE ENTRADA(data/entradas.csv):
﻿Mês;Descrição;Valor
01/06/2026;Conta;3089
01/06/2026;Venda do Carro;8064,96
01/06/2026;NuBank;12907,65
01/07/2026;Salário;0
01/08/2026;Salário;9000
01/09/2026;Salário;9000
01/10/2026;Salário;9000
01/01/2027;Salário;9000
01/02/2027;Salário;9000
...
DADOS DE SAÍDA(data/saidas.csv):
﻿﻿Mês;Item;Descrição;Valor
01/06/2026;CRECHE;MATEUS;0
01/07/2026;CRECHE;MATEUS;860
01/08/2026;CRECHE;MATEUS;860
01/09/2026;CRECHE;MATEUS;860
01/10/2026;CRECHE;MATEUS;860
01/11/2026;CRECHE;MATEUS;860
01/12/2026;CRECHE;MATEUS;860
01/01/2027;CRECHE;MATEUS;860
01/02/2027;CRECHE;MATEUS;860
01/03/2027;CRECHE;MATEUS;860
01/04/2027;CRECHE;MATEUS;860
...
LISTA DE DESEJO(data/lista.csv):
﻿
```
---

## Exemplo de Contexto Montado

> Mostre um exemplo de como os dados são formatados para o agente.

```
Dados de Entrada:
- Mês: 01/06/2026
- Descrição: Salário
- Valor: R$ 9.000

Dados de Saída:
- Mês: 01/06/2026
- Item : CRECHE
- Descrição : MATEUS
- Valor : R$ 860
...
```
