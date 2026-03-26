# Tela: Vagas

## Objetivo
Permitir que o administrador visualize, gerencie e edite as vagas publicadas pelas empresas na plataforma.

A tela apresenta uma listagem das vagas cadastradas e permite acessar seus detalhes, editar informações e visualizar candidatos inscritos.

---

## URL
/job

---

# Campos da Tabela

| Campo | Tipo | Obrigatório |
|------|------|------|
| Código | número | sim |
| Data Publicação | datetime | sim |
| Status | texto | sim |
| Título | texto | sim |
| Empresa | texto | sim |
| CNPJ | texto | não |
| Forma de Pagamento | texto | não |
| Status do Pagamento | texto | não |
| Valor | número | não |
| Responsável | texto | não |
| Telefone Responsável | texto | não |
| Quantidade de Candidatos | número | não |
| Nº NF | texto | não |

---

# Ações

Visualizar Vaga  
Abrir os detalhes completos da vaga.

Editar Vaga  
Abrir formulário para edição da vaga.

Inativar Vaga  
Desativar a vaga no sistema.

Exportar Dados  
Exportar informações da vaga em xlsx.

---

# Visualização da Vaga

Ao clicar em uma vaga na tabela o sistema abre um **modal com os detalhes da vaga**.

---

## Informações exibidas

Identificação da vaga

- Código da vaga
- Título da vaga
- Empresa
- Logo da empresa

---

Descrição da vaga

Texto completo com as informações da vaga.

Exemplo:

- descrição da função
- atividades da vaga
- requisitos
- informações da empresa

---

Local de trabalho

Informações do endereço da vaga.

- bairro
- cidade
- referência de localização

---

Jornada de trabalho

- horário de início
- horário de término
- observações de jornada

---

# **Salário (NÃO TEM NO ADMIN, MAS DEVERIA TER)**

O salário da vaga deve ser exibido de forma clara na visualização da vaga.

Exemplo:

Salário:
R$ 2.000,00

Esse valor representa a remuneração da vaga anunciada.

---

Benefícios

Lista de benefícios oferecidos na vaga.

Exemplos:

- Seguro de Vida
- TotalPass
- Vale Transporte
- Vale Refeição
- Plano de Saúde
- Plano Odontológico

---

# Informações da publicação

| Campo | Descrição |
|------|------|
| Postado | Data de publicação da vaga |
| Expira em | Data de expiração da vaga |
| Status | Situação da vaga |
| Confidencial | Indica se a empresa está oculta |
| Empresa | Nome da empresa |
| Responsável | Pessoa responsável pela vaga |
| Fone | Telefone de contato |
| Email | Email de contato |

**falta salário aqui**

---

# Informação do pacote

Quando aplicável o sistema exibe:
Vaga publicada através da utilização de crédito de pacote de vagas

---

# Candidatos da vaga

Lista de candidatos que se aplicaram para a vaga.

| Campo | Tipo |
|------|------|
| Nome | texto |
| Sexo | texto |
| Idade | número |
| Data de Aplicação | datetime |
| Distância | número |
| Educação | texto |
| Email | texto |
| Telefone | texto |

---

## Ações disponíveis para candidatos

Ver CV  
Visualizar currículo do candidato.

Editar CV  
Editar informações do candidato.

WhatsApp  
Abrir conversa com o candidato.

---

# Editar Vaga

Ao clicar em **Editar Vaga**, o sistema abre um formulário completo de edição da vaga.

---

## Informações do estabelecimento

| Campo | Tipo |
|------|------|
| Empresa | texto |
| Site | texto |
| Nome do responsável | texto |
| Sobrenome do responsável | texto |
| Telefone | texto |
| Email | texto |
| Documento | texto |

---

## Logo da empresa

É possível inserir ou alterar o logotipo da empresa.

Função:

- melhorar apresentação da vaga
- melhorar visibilidade no site

---

# Endereço da vaga

| Campo | Tipo |
|------|------|
| CEP | texto |
| Logradouro | texto |
| Número | texto |
| Complemento | texto |
| Bairro | texto |
| Estado | select |
| Cidade | select |
| Latitude | número |
| Longitude | número |

---

# Detalhes da vaga

| Campo | Tipo |
|------|------|
| Título da vaga | texto |
| Início da jornada | horário |
| Fim da jornada | horário |
| Descrição da vaga | texto longo |

---

# Informações do cargo

| Campo | Tipo |
|------|------|
| Área | select |
| Cargo | select |
| Tipo de contrato | select |
| Faixa salarial | select |

---

# Benefícios disponíveis

Benefícios podem ser selecionados individualmente.

- Almoço no local
- Comissão
- Participação nos lucros
- Plano odontológico
- Plano de saúde
- Seguro de vida
- Vale refeição
- Vale transporte

---

# Opções da vaga

| Campo | Tipo |
|------|------|
| Pessoa com deficiência | boolean |
| Vaga confidencial | boolean |

---

# Perguntas para candidatos

É possível cadastrar ou excluir perguntas que serão exibidas durante a candidatura.

Exemplos:

- Possui fácil acesso à região da vaga?
- Possui experiência na função?
- Possui disponibilidade para banco de horas?
- Possui disponibilidade para horário da tarde?

---

# Ações do formulário

Salvar Vaga  
Salvar alterações realizadas na vaga.

Cancelar  
Cancelar a edição da vaga.

---

# API

GET /jobs  
Retorna listagem de vagas.

GET /jobs/{id}  
Retorna detalhes da vaga.

POST /jobs  
Cria nova vaga.

PUT /jobs/{id}  
Atualiza uma vaga.

DELETE /jobs/{id}  
Remove uma vaga.

GET /jobs/export  
Exporta vagas do sistema.