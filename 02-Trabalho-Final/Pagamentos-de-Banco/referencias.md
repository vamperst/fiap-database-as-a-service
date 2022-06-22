## Como enfrentar este desafio

**Quais são os padrões de acesso?**

Os padrões de acesso no cenário são descritos como:

1. Insira pagamentos agendados.
2. Retorne pagamentos agendados pelo usuário pelos próximos 90 dias.
3. Pagamentos de devolução entre os usuários para data específica por status (`agendado` ou` pendente`).

Identifique possíveis chaves de partições para atender ao padrão de acesso primário:

- Qual atributo do item (*conta*,*agendado*,*status*,*datablob*) escala com padrões de acesso?
- O que é uma organização natural para os itens de pagamento relacionados (para devolver itens coletados em relação aos padrões de acesso acima)?
- Considere a dimensão do acesso: leituras e gravações.
Ao determinar como organizar itens relacionados ao padrão de acesso primário:

- Com quais itens da organização os itens precisam ser escritos para devolver itens pelo usuário para um intervalo de data (classificar por)?
- Qual é a hierarquia dos relacionamentos e quando se aplica (mais geral a mais específica)?

Cumprindo os terceiros padrões de acesso:

- O terceiro padrão de acesso é OLTP e pode ser cumprido diretamente no DynamoDB



#### Referências úteis

Dado o exposto acima, veja abaixo algumas referências úteis.
- **[Melhores práticas para usar teclas de classificação para organizar dados](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/bp-sort-keys.html)**
- **[Trabalhando com consultas](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/Query.html)**
- **[Usando índices secundários globais no DynamoDB](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/GSI.html)**
- **[Escreva Shard A GSI para consultas seletivas no DynamoDB](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/bp-indexes-gsi-sharding.html)**
