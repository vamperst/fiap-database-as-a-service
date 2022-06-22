##  Desafio do carrinho de varejo

Uma loja de varejo on -line pediu que você projete a camada de armazenamento de dados e a (s) tabela (s) NoSQL (s).O site atende clientes e os produtos que eles visualizam, economizam e compram.Atualmente, o tráfego do site está baixo, mas eles querem ser capazes de atender a milhões de clientes simultâneos.

- Os clientes interagem com os produtos que podem ser `ativo`,`salvo` ou 'adquiridos'. Uma vez que forem 'comprados`, eles receberão um *OrderId *.
- Os produtos têm os seguintes atributos: *AccountId*, *status*(`ativo`,`salvo` ou `adquirido`), *createTimestamp*e *itensku*(o tamanho do item total é <= 1 kb).
- Quando um cliente abre o aplicativo da loja de varejo, ele visualiza os produtos ativos em seu carrinho, que são organizados por mais recentemente.
- Os usuários podem visualizar os produtos que salvaram mais tarde, que são organizados por mais recentemente salvos.
- Os usuários podem visualizar os produtos que compraram, que são organizados por mais recentemente.
- As equipes de produtos têm a capacidade de consultar regularmente em todos os clientes para identificar as pessoas que possuem um produto específico em sua conta que é `ativo`,`salvo` ou `adquirido '.
- A equipe de inteligência de negócios precisa executar várias consultas ad hoc complexas contra o conjunto de dados para criar relatórios semanais e mensais.

Crie um modelo de dados NoSQL para atender ao componente OLTP da carga de trabalho. Como você cumpriria os requisitos da equipe de BI?