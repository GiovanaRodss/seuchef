# Tela: Cupons

## Objetivo
Permitir que o administrador gerencie cupons de desconto utilizados na plataforma.

Os cupons podem ser utilizados para aplicar descontos em compras ou pacotes disponíveis no sistema.

---

## URL
/coupons

---

## Campos

| Campo | Tipo | Obrigatório |
|------|------|------|
| Name | texto | sim |
| Tipo de Desconto | enum | sim |
| Valor do Desconto | decimal | sim |
| Tipo Expiração | enum | sim |
| Data Início | datetime | não |
| Data Fim | datetime | não |
| Contador de Uso | número | não |
| Limite de Uso | número | não |
| Restrição de Pacote | lista | não |
| Apenas 1ª Compra | boolean | não |

---

## Ações

Add  
Criar um novo cupom de desconto.

Edit  
Editar as informações do cupom selecionado.

Delete  
Excluir um cupom do sistema.

Update  
Salvar alterações feitas em um cupom.

Cancel  
Cancelar a edição do cupom.

Busca  
Filtrar cupons na tabela através dos campos disponíveis.

---

## Funções do Cupom

### Nome
Identificador único do cupom utilizado pelos usuários na plataforma.

Exemplo:
- PRIMEIRACOMPRA10
- BLACKFRIDAY20
- CLIENTE30

---

### Tipo de Desconto
Define o tipo de desconto aplicado.

Opções possíveis:

Percentual  
O desconto será aplicado em porcentagem sobre o valor da compra.

Valor Fixo  
O desconto será aplicado como um valor fixo.

---

### Valor do Desconto
Define o valor aplicado ao desconto.

Exemplo:

- 10% de desconto
- R$10 de desconto

---

### Tipo de Expiração

Define a regra de validade do cupom.

Possíveis regras:

Quantidade de Uso  
O cupom expira após atingir um número máximo de utilizações.

Data  
O cupom expira após uma data definida.

---

### Data Início
Define quando o cupom passa a ser válido.

---

### Data Fim
Define quando o cupom deixa de ser válido.

---

### Contador de Uso
Quantidade de vezes que o cupom já foi utilizado.

Esse campo é atualizado automaticamente pelo sistema.

---

### Limite de Uso
Quantidade máxima de vezes que o cupom pode ser utilizado.

Quando o limite é atingido, o cupom deixa de ser válido.

---

### Restrição de Pacote
Define em quais pacotes o cupom pode ser utilizado (campo multipla escolha).

Exemplo:                                                                                                       
- AV
- P3
- P5
- P10

---

### Apenas 1ª Compra
Quando ativado, o cupom só pode ser utilizado na **primeira compra do usuário**.

---

## Fluxo

Acessar página de cupons  
↓  
Sistema exibe a tabela de cupons cadastrados  
↓  
Administrador pode:

- criar novo cupom
- editar cupom existente
- excluir cupom
- aplicar filtros na listagem

Ao editar ou criar um cupom:

Administrador  
↓  
Abre formulário de cupom  
↓  
Preenche os campos  
↓  
Salva alterações

---

## API

GET /coupons  
Retorna a listagem de cupons cadastrados.

GET /coupons/{id}  
Retorna os detalhes de um cupom.

POST /coupons  
Cria um novo cupom.

PUT /coupons/{id}  
Atualiza os dados de um cupom.

DELETE /coupons/{id}  
Remove um cupom do sistema.