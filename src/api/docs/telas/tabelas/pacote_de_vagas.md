# Tela: Pacote de Vagas

## Objetivo
Permitir que o administrador tenha acesso as empresas que compram qualquer item no site.

Tabela com informações das empresas

## Campos
NOME | CNPJ | CRÉDITOS | ÚLTIMO PAGAMENTO | ULTIMO PACOTE | VALOR | RESPONSÁVEL | TELEFONE RESPONSÁVEL

---

## URL
/publishingcredits

---

## Ações

### Visualizar detalhes do pacote

Ao clicar em uma linha da tabela de pacotes de vagas, o sistema abre um **modal com os detalhes da empresa e dos créditos**.

O modal exibe:

- Nome da empresa
- CNPJ
- Inscrição Estadual
- Responsável
- Telefone
- Email
- Créditos restantes

Também exibe os dados do pacote adquirido:

- Nome do pacote
- Status do processamento
- Status do pagamento
- Chave PIX
- Valor
- Data
- Código da transação
- Referência
- Nome da empresa

Além disso, o modal apresenta a listagem de vagas vinculadas ao pacote.

---

### Atualizar créditos manualmente

O usuário pode informar uma quantidade no campo de créditos e clicar em **Atualizar**.

Resultado esperado:

- o sistema altera manualmente a quantidade de créditos da empresa
- a quantidade atualizada passa a ser refletida no saldo de créditos restantes

---

### Atualizar NF

O usuário pode informar o número da nota fiscal no campo **Nº NF** e clicar em **Salvar**.

Resultado esperado:

- o sistema salva o número da nota fiscal vinculado ao pacote exibido

---

### Fechar modal

Ao clicar em **X**, o sistema fecha o modal e retorna para a listagem de pacotes de vagas.

---

### Exportar dados

Ao clicar em **Exportar Dados**, o sistema gera um arquivo com a listagem de pacotes de vagas.

---

## Fluxo

### 1. Listagem de pacotes

Admin acessa a página:

`/publishingcredits`

O sistema exibe uma tabela contendo:

- Nome
- CNPJ
- Créditos
- Último Pagamento
- Último Pacote
- Valor
- Responsável
- Telefone Responsável

Também são disponibilizadas as seguintes funcionalidades:

- filtros por coluna
- paginação
- exportação de dados

---

### 2. Visualizar detalhes do pacote

Fluxo:

Admin  
↓  
Clica em uma linha da tabela  
↓  
Sistema abre modal com detalhes da empresa e do pacote  
↓  
Exibe informações completas do pacote e créditos

---

### 3. Atualizar créditos manualmente

Fluxo:

Admin  
↓  
Abre modal da empresa  
↓  
Informa nova quantidade de créditos  
↓  
Clica em **Atualizar**  
↓  
Sistema atualiza o saldo de créditos da empresa

---

### 4. Salvar número da nota fiscal

Fluxo:

Admin  
↓  
Abre modal da empresa  
↓  
Preenche o campo **Nº NF**  
↓  
Clica em **Salvar**  
↓  
Sistema grava o número da nota fiscal no pacote

---

### 5. Consultar vagas vinculadas

Fluxo:

Admin  
↓  
Abre modal da empresa  
↓  
Visualiza a seção **Vagas**  
↓  
Consulta os códigos e títulos das vagas associadas ao pacote

---

### 6. Fechar visualização

Fluxo:

Admin  
↓  
Clica em **X**  
↓  
Modal é fechado  
↓  
Admin retorna para a tabela de pacotes

---

## API

### Listar pacotes de vagas

**Endpoint**  
`GET /publishingcredits`

**Objetivo**  
Retornar a listagem de pacotes de vagas exibida na tabela principal.

**Campos esperados**
- id
- company_name
- cnpj
- credits
- last_payment_date
- last_package
- amount
- responsible_name
- responsible_phone

**Query params sugeridos**
- page
- per_page
- company_name
- cnpj
- package_name
- responsible_name

**Usado em**
- carregamento inicial da tela
- filtros
- paginação
- exportação

---

### Buscar detalhes do pacote

**Endpoint**  
`GET /publishingcredits/{id}`

**Objetivo**  
Retornar os detalhes completos da empresa, do pacote e das vagas vinculadas.

**Campos esperados**
- id
- company_name
- cnpj
- state_registration
- responsible_name
- responsible_phone
- responsible_email
- credits_remaining
- package_name
- processing_status
- payment_status
- pix_key
- amount
- payment_date
- transaction_code
- reference
- invoice_number
- jobs[]

**Estrutura sugerida de jobs[]**
- job_id
- code
- title

**Usado em**
- abertura do modal de detalhes

---

### Atualizar créditos manualmente

**Endpoint**  
`PUT /publishingcredits/{id}/credits`

**Objetivo**  
Atualizar manualmente a quantidade de créditos da empresa.

**Body esperado**
json
{
  "credits": 10
} 

---

### Salvar número da nota fiscal

**Endpoint**  
`PUT /publishingcredits/{id}/invoice-number`

**Objetivo**  
Salvar ou atualizar o número da nota fiscal do pacote.

**Body esperado**

json
{
  "invoice_number": "12345"
} 

### Exportar pacotes de vagas

**Endpoint**  
`GET /publishingcredits/export`

**Objetivo**  
Exportar a listagem de pacotes de vagas.

**Formatos suportados**

- csv  
- xlsx  

**Query params**

| Parâmetro | Tipo | Descrição |
|-----------|------|-----------|
| company_name | string | Filtrar por nome da empresa |
| cnpj | string | Filtrar por CNPJ |
| package_name | string | Filtrar por tipo de pacote |
| page | integer | Página da listagem |
| per_page | integer | Quantidade de registros por página |

**Exemplo de requisição**

```http
GET /publishingcredits/export?company_name=Piatto&page=1&per_page=50