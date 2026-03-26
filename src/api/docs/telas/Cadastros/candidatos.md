# Tela: Candidatos

## Objetivo
Permitir que o administrador visualize e gerencie os candidatos cadastrados no sistema.

A tela apresenta uma listagem dos candidatos registrados na plataforma e permite editar seus dados cadastrais.

---

## URL
/candidate

---

## Campos da Tabela

| Campo | Tipo | Obrigatório |
|------|------|------|
| Nome | texto | sim |
| CPF | texto | sim |
| E-mail | texto | sim |
| Data Cadastro | datetime | sim |

---

## Campos do Modal de Edição

| Campo | Tipo | Obrigatório |
|------|------|------|
| Nome | texto | sim |
| CPF | texto | sim |
| E-mail | texto | sim |
| Data Cadastro | date | não |
| CEP | texto | não |
| Logradouro | texto | não |
| Complemento | texto | não |
| Bairro | texto | não |
| Estado | texto | não |
| Cidade | texto | não |

---

## Ações

Edit  
Abrir o modal do candidato selecionado para edição dos dados cadastrais.

Delete  
Excluir o candidato selecionado do sistema.

Save  
Salvar alterações feitas no cadastro do candidato.

Cancel  
Cancelar a edição e fechar o modal sem salvar.

Exportar Dados  
Exportar a listagem de candidatos em xlsx.

Busca  
Filtrar candidatos através dos campos da tabela.

---

## Fluxo

Acessar página de candidatos  
↓  
Sistema exibe a tabela com os candidatos cadastrados  
↓  
Administrador pode:

- pesquisar candidatos
- selecionar um candidato
- editar um candidato
- excluir um candidato
- exportar os dados em xlsx

---

### Fluxo de edição do candidato

Administrador  
↓  
Seleciona um candidato na tabela  
↓  
Sistema abre modal com os dados do candidato  
↓  
Administrador altera as informações desejadas  
↓  
Clica em **SAVE** para salvar  
ou  
Clica em **CANCEL** para fechar sem salvar

---

## API

GET /candidates  
Retorna a listagem de candidatos.

GET /candidates/{id}  
Retorna os detalhes de um candidato para exibição no modal.

PUT /candidates/{id}  
Atualiza os dados do candidato.

DELETE /candidates/{id}  
Remove um candidato do sistema.

GET /candidates/export  
Exporta a listagem de candidatos.