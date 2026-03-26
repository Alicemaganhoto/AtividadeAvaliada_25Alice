# Avaliação — Engenharia de Software
**Sistema Integrado de Gestão de Farmácia — MVP Definido pelo Estudante**

Aluno: Alice dos Santos Maganhoto
RA: 25000188  
Data: 25/03/26

---

# 1. Definição do MVP
Descreva aqui **qual parte do sistema** foi incluída no seu MVP.  
Explique claramente:

- O que está **dentro** do MVP
> Controle de estoque de acordo com as vendas, controle de devolução e gerenciamento de contas a pagar e a receber.
  
- O que está **fora** do MVP
> Manipulação de remédios, aplicativo de vendas e entregas e venda drive-thru. 
   
- Por que você fez essas escolhas
> meu MVP consegue controlar tudo que entra no sistema da farmácia, como vendas, estoque, á pagar e receber e identificar quando ocorrer devolução. E a parte do drive thru e vendas pelo APP, decidimos deixar para o futuro, pois ainda não é algo necessário no momento. E a manipulação também é algo que a farmácia não trabalha, por enquanto só existem vendas de remédios prontos.

Exemplo de início:  
> “Meu MVP cobre o processo de venda desde a identificação/cadastro do cliente até a emissão do comprovante, incluindo tratamento de estoque insuficiente.”

---

# 2. Regras de Negócio (mínimo: 5)
Liste e descreva **cada RN** de forma clara.

**RN01 —** = venda de remédio controlados, como antibióticos que precisam de receita e vistoria de uma farmaceutica.
**RN02 —** = cancelar estoque negativo, vendas de produtos com saldo zero serão travadas pelo sistema.
**RN03 —** = aprovar crédito, vendas a prazo, só pode ser feita por clientes que são cadastrados.
**RN04 —** = atualizar saldo, toda entrada por compra ou saída deve ser atualizada no exato momento.
**RN05 —** = registrar lançamento financeiro, toda compr que for confirmada pelo vendedor deve ser gerado "contas á pagar".

(Adicione mais se quiser.)

---

# 3. Requisitos Funcionais (mínimo: 8)
Liste os requisitos funcionais do seu MVP.

**RF01 —** = Pesquisar produtos por nome ou código de barras.
**RF02 —** = ao realizar venda de produtos, tera baixa no estoque.
**RF03 —** = cadastrar informações dos clientes.
**RF04 —** = registrar quando alguém devolver algum produto com estorno no estoque.
**RF05 —** = enviar compras de vendedores para reposição de mercadoria.
**RF06 —** = criar contas a receber para vendas feitas a prazo.
**RF07 —** = consultar relatórios de produtos mais vendidos e estoque mínimo.
**RF08 —** = validar usuários com diferentes níveis de permissão.

(Adicione mais se quiser.)

---

# 🛡 4. Requisitos Não Funcionais (mínimo: 4)
Liste os RNFs do sistema conforme seu MVP.

**RNF01 —** = segurança: o sistema deve exigir login e senha para impedir acesso de pessoas mal-intencionadas.
**RNF02 —** = comportamento: a consulta de estoque não deve demorar mais do que 2 segundos.
**RNF03 —** = disponibilidade: o sistema deve trabalhar de forma consistente 99% do tempo, no momento de funcionamento da rede.
**RNF04 —** = usabilidade: a interface de vendas deve ser de fácil compreensão, permitindo concluir uma operação em menos de 5 cliques.

(Adicione mais se quiser.)

---

# 5. Casos de Uso (mínimo: 10)
### Inserir **diagrama de casos de uso geral**, demonstrando claramente:
- os 10 casos
- relação entre eles e atores
- pelo menos 3 includes
- pelo menos 3 extends

## **UC01 — Registrar Perda de Medicamento (Ator - Farmacêutico)

- O que faz: Utilizado para anotar no sistema quando um remédio venceu ou foi aberto e não pode mais ser vendido.
## **UC02 — Transferência de Estoque entre Unidades (Ator: - Gerente)

- O que faz: Realiza o transporte de produtos de uma farmácia para outra dentro da mesma rede.

## **UC03 — Aplicar Desconto de Convênio (Ator: - Atendente)

- Relacionamento: extend do UC01
- O que faz: Aplica o desconto do convênio na hora da compra.

## **UC04 — Consultar Histórico de Compras do Cliente (Ator: - Atendente)

- Relacionamento: extend do UC01
- O que faz: Mostra o que o cliente já comprou antes.

## **UC05 — Efetuar o Fechamento de Caixa (Ator: - Atendente)

- O que faz: Ao terminar o turno, o atendente verifica todas as entradas no caixa, incluindo dinheiro e cartão.

## **UC06 — Baixar Conta a Receber (Ator - Financeiro)

- O que faz: Registra quando o cliente paga uma compra que ele tinha deixado pra pagar depois.

## **UC07 — Efetuar Pagamento de Fornecedor (Ator - Financeiro)

- O que faz: Marca como “pago” uma conta que a farmácia tinha com algum fornecedor.
## **UC08 — Consultar Histórico de Compras do Cliente (Ator - Atendente)

- Relacionamento: extend do UC01
- O que faz: Mostra o que o cliente costuma comprar, ajudando a atender mais rápido e sugerir produtos.

## **UC09 — Fechamento de Caixa Diário (Ator - Atendente)

- O que faz: Confere tudo do caixa no final do dia pra ver se tá tudo certo.

## **UC10 — Checar Movimentação de Estoque (Ator - Administrador)

- O que faz: Mostra um relatório dizendo o que entrou, o que saiu, quem mexeu e o motivo.

<img width="2866" height="373" alt="image" src="https://github.com/user-attachments/assets/9fc9adab-3140-4fcc-8f6a-8e0d66b90252" />


---

# 6. Documentação dos Casos de Uso
Para **cada caso de uso**, utilize o template abaixo:
---

## **UC01 — Registrar Perda de Medicamento

Ator(es): Farmacêutico
Descrição: Serve para registrar no sistema quando um remédio venceu ou foi aberto e não pode mais ser vendido.
Pré-condições: O remédio já precisa estar registrado no sistema
Pós-condições: A perda fica registrada e o estoque diminui automaticamente.

<img width="480" height="395" alt="image" src="https://github.com/user-attachments/assets/c96227bb-b803-4041-a9f6-d72c37483276" />

## **UC02 — Transferir Estoque entre Unidades

Ator(es): Gerente
Descrição: Serve para o gerente enviar produtos de uma farmácia para outra da rede.
Pré-condições: O produto precisa ter quantidade disponível no estoque.
Pós-condições: O sistema registra a transferência e atualiza o estoque das duas unidades.

<img width="449" height="287" alt="image" src="https://github.com/user-attachments/assets/118b2067-76e6-4a4a-91ef-555433dae540" />

## **UC03 —Aplicar Desconto de Convênio

Ator(es): Atendente
Descrição: Aplica o desconto do convênio na compra do cliente, caso ele tenha convênio ativo.
Pré-condições: O cliente precisa informar o CPF e ter convênio válido.
Pós-condições: O sistema aplica o desconto e atualiza o valor da compra.

<img width="347" height="287" alt="image" src="https://github.com/user-attachments/assets/09b415b4-bb20-419c-ad8b-e17c95331cef" />

## **UC04 —Consultar Histórico de Compras do Cliente

Ator(es): Atendente
Descrição: Permite ver o que o cliente já comprou antes, ajudando a atender mais rápido.
Pré-condições: O cliente precisa ser identificado pelo CPF.
Pós-condições: O histórico aparece na tela para consulta.

<img width="815" height="419" alt="image" src="https://github.com/user-attachments/assets/61fbfd47-eb1a-4359-a796-f151710f3de3" />

## **UC05 — Efetuar Fechamento de CaixaAtor(es): Atendente

Descrição: No fim do turno, o atendente confere o dinheiro e cartão para fechar o caixa.
Pré-condições: As vendas do turno precisam estar registradas no sistema.
Pós-condições: O caixa é fechado e o sistema salva os valores.

<img width="329" height="287" alt="image" src="https://github.com/user-attachments/assets/91b0a5ba-5934-433d-a0a3-d812769d0507" />

## **UC06 — Baixar Conta a Receber

Ator(es): Financeiro
Descrição: Registra quando o cliente paga uma dívida antiga.
Pré-condições: A dívida precisa estar registrada no sistema como pendente.
Pós-condições: A conta muda para “paga” e fica registrada como quitada.

<img width="428" height="449" alt="image" src="https://github.com/user-attachments/assets/fdc7539b-2dbe-4293-9f4b-528ad91aaada" />

## **UC07 — Efetuar Pagamento de Fornecedor

Ator(es): Financeiro
Descrição: Serve para marcar no sistema que a farmácia pagou um fornecedor.
Pré-condições: A conta do fornecedor precisa estar cadastrada no sistema.
Pós-condições: A conta passa a aparecer como “paga”.

<img width="413" height="449" alt="image" src="https://github.com/user-attachments/assets/204c1c37-0d2d-4e08-9cd6-0dd29eff9816" />

## **UC08 — Consultar Histórico de Compras (Sugestões)

Ator(es): Atendente
Descrição: Mostra o que o cliente costuma comprar para ajudar no atendimento.
Pré-condições: O cliente precisa estar identificado no sistema (CPF).
Pós-condições: O sistema exibe as compras mais frequentes do cliente.

<img width="546" height="341" alt="image" src="https://github.com/user-attachments/assets/8aba1262-1bc1-43ac-b978-dc45ea09d55d" />

## **UC09 —Fechamento de Caixa Diário

Ator(es): Atendente
Descrição: No fim do dia, o atendente confere o caixa e fecha tudo no sistema.
Pré-condições: As vendas do dia precisam estar registradas.
Pós-condições: O sistema salva o fechamento diário e gera o registro do caixa.

<img width="312" height="287" alt="image" src="https://github.com/user-attachments/assets/919e9df6-f252-4ab2-a3e1-ec631abbd74a" />

## **UC10 — Checar Movimentação de Estoque

Ator(es): Administrador
Descrição: Permite ver tudo que entrou e saiu do estoque, incluindo quem fez a alteração e o motivo.
Pré-condições: O administrador precisa ter acesso ao sistema.
Pós-condições: O relatório do estoque é exibido para consulta.

<img width="521" height="341" alt="image" src="https://github.com/user-attachments/assets/1d9b1b2c-e937-4422-bf9c-da522ac9d0aa" />

---

