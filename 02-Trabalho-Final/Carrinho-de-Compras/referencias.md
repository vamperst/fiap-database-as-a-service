## Como enfrentar este desafio

**Quais são os padrões de acesso?**

Os padrões de acesso no cenário são:

1. Insira e atualize itens colocados em um carrinho pelos usuários.
2. Retorne itens relacionados a um usuário (*conta*), classificado por *createTimestamp* e escopo para um status *específico*.
3. Retorne os itens do usuário por *itensku*, classificados por *createTimestamp* e escopo para um status *específico*.
4. Consultas ad hoc offline para equipe de inteligência de negócios.
Identifique possíveis chaves de partição para cumprir o padrão de acesso primário:

- Qual item de escalas de atributo em volume junto com maior acesso?
- O que é uma organização natural para os itens de dados relacionados (para retornar itens coletados em relação aos padrões de acesso acima)?
- Considere a dimensão do acesso: leituras e gravações.
Ao determinar como organizar itens relacionados ao padrão de acesso primário:

- Que organização precisa ser escrita para devolver itens em ordem classificada (classificar por)?
- Qual é a hierarquia dos relacionamentos (mais geral a mais específica)?

Cumprindo o segundo e o terceiro padrões de acesso:

- O segundo padrão de acesso é um padrão de acesso OLTP e pode ser modelado diretamente no DynamoDB
- O terceiro padrão de acesso é OLAP e não precisa ser cumprido diretamente no DynamoDB
- 
#### Referências úteis

Dado o exposto acima, veja abaixo algumas referências úteis.
- **[Melhores práticas para usar teclas de classificação para organizar dados](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/bp-sort-keys.html)**
- **[Trabalhando com consultas no DynamoDB](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/Query.html)**
- **[Usando índices secundários globais no DynamoDB](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/GSI.html)**
- **[Como realizar análises avançadas e criar visualizações de seus dados do Amazon DynamoDB usando a Amazon Athena](https://aws.amazon.com/blogs/database/how-to-perform-advanced-analytics-and-build-visualizations-of-your-amazon-dynamodb-data-by-using-amazon-athena/)**
