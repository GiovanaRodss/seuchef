# Tela: Candidatos

## Objetivo
Permitir que o administrador visualize e gerencie as empresas cadastradas no sistema.

A tela apresenta uma listagem das empresas registradas na plataforma e permite editar seus dados cadastrais.

---

## URL
/company

---

## Campos da Tabela

| Campo | Tipo | Obrigatório |
|------|------|------|
| Razão Social | texto | sim |
| Nome Fantasia | texto | não |
| CNPJ | texto | sim |
| E-mail | texto | sim |
| Telefone | texto | sim |
| Data Cadastro | datetime | sim |

---

## Campos do Modal de Edição

| Campo | Tipo | Obrigatório |
|------|------|------|
| Razão Social | texto | sim |
| Nome Fantasia | texto | não |
| CNPJ | texto | sim |
| E-mail | texto | sim |
| Telefone | texto | sim |
| Data Cadastro | datetime | sim |

---

## Ações

Edit  
Abrir o modal da empresa selecionado para edição dos dados cadastrais.

Delete  
Excluir a empresa selecionada do sistema.

Save  
Salvar alterações feitas no cadastro da empresa.

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
Sistema exibe a tabela com as empresas cadastrados  
↓  
Administrador pode:

- pesquisar candidatos
- selecionar um candidato
- editar um candidato
- excluir um candidato
- exportar os dados em xlsx

---

### Fluxo de edição da empresa

Administrador  
↓  
Seleciona um candidato na tabela  
↓  
Sistema abre modal com os dados da empresa  
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
Atualiza os dados da empresa.

DELETE /candidates/{id}  
Remove um candidato do sistema.

GET /candidates/export  
Exporta a listagem de candidatos.