
## Cenário de pagamentos bancários

Um banco pediu que você desenvolvesse um novo sistema de back-end para lidar com seus pagamentos programados.

Esta é principalmente uma carga de trabalho OLTP com processos diários de lote.Os itens da tabela (s) representam pagamentos programados entre contas.À medida que os itens são inseridos, eles são agendados em uma data específica para ter o pagamento processado.Todos os dias, os itens são enviados regularmente para um sistema transacional para processamento, momento em que seu status altera para `pendente`.Após uma transação bem -sucedida, o status de um item é definido como `processado` e atualizado com um novo ID de transação.

#### Workload dimensions

- As contas podem ter vários pagamentos agendados para qualquer dia no futuro.
- Os pagamentos têm os seguintes campos de dados: *AccountId *, *agendado *, *status *(`agendado`,`pendente` ou `processado`), *datablob *(o tamanho do item total é <= 8 kb)
- Um milhão de pagamentos agendados automatizados são adicionados todos os dias às 1:00 da manhã *para esse dia *, que precisam ser concluídos em 30 minutos.
- Um milhão de pagamentos são adicionados todos os dias com o estado `programado`, principalmente nas horas das 6h às 18h.
- Durante o dia, um trabalho em lote funciona regularmente para consultar os pagamentos de hoje `agendados`. Este serviço envia os itens `agendados` para o serviço de transação. Ao enviar os itens para o serviço de transação, o status de pagamento é alterado para `pendente`.
- Quando o serviço de transação é concluído, o status de um item é alterado para `processado` e um novo ID de transação é adicionado ao item.
- Os itens precisam ser devolvidos para uma conta específica programada para pagamento nos próximos 90 dias.
- O serviço transacional deve recuperar todos os itens para uma data específica (por exemplo, hoje) em todas as contas. Ele deve poder recuperar itens especificamente `agendados` ou `pendente`.

**Seu desafio:** Desenvolva um modelo de dados NoSQL para o banco que atenda aos requisitos de pagamento agendados.
