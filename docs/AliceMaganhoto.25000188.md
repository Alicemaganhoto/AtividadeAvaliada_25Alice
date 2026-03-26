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

<img width="1394" height="741" alt="image" src="https://github.com/user-attachments/assets/eabaa0d1-7e74-4c4b-870a-c975b2a260a8" />

---

# 6. Documentação dos Casos de Uso
Para **cada caso de uso**, utilize o template abaixo:
---
## **UC01 — Registrar Perda de Medicamento**
Ator(es): Farmacêutico.
Descrição: Registro de produtos que saíram do estoque por vencimento ou avaria.
Pré-condições: Usuário logado e produto cadastrado no sistema.
Pós-condições: Estoque atualizado com a baixa do item e motivo registrado.
 

Fluxo Principal
O Farmacêutico acessa o módulo de estoque e seleciona "Registrar Perda".

O sistema solicita a identificação do produto (código de barras ou nome).

O Farmacêutico informa a quantidade e o motivo (Ex: Vencimento).

O sistema confirma a operação e abate o saldo do estoque.

Fluxos Alternativos / Exceções
EX01 — Produto não encontrado: O sistema alerta que o código é inválido.

EX02 — Quantidade maior que estoque: O sistema impede a baixa negativa.

UC02 — Transferir Estoque entre Unidades
Ator(es): Gerente.
Descrição: Movimentação física e lógica de produtos entre filiais da rede.
Pré-condições: Saldo disponível na unidade de origem e unidade de destino ativa.
Pós-condições: Saldo diminuído na origem e registrado como "em trânsito" para o destino.

Fluxo Principal
O Gerente seleciona a unidade de destino.

O Gerente informa os itens e quantidades para transferência.

O sistema valida a disponibilidade do estoque local.

O sistema gera a guia de transporte e atualiza o estoque.

Fluxos Alternativos / Exceções
EX01 — Unidade destino inexistente: O sistema solicita correção do destino.

UC03 — Aplicar Desconto de Convênio
Ator(es): Atendente.
Descrição: Aplicação de descontos automáticos baseados em parcerias.
Pré-condições: Venda em andamento (UC00) e cliente identificado.
Pós-condições: Valor total da venda recalculado com o desconto.

Fluxo Principal
Durante a venda, o Atendente seleciona a opção "Convênio".

O sistema verifica o tipo de convênio vinculado ao cliente.

O sistema aplica o percentual de desconto sobre os itens permitidos.

O valor total é atualizado na tela de venda.

Relacionamentos
Extend: UC00 (Realizar Venda) — Condição: Cliente possui convênio ativo.

---

