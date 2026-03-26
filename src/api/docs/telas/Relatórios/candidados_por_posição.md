# Tela: Relatório de Candidaturas por Posição

## Objetivo
Permitir que o administrador visualize e exporte um relatório de candidaturas realizadas na plataforma, filtrando por período e cargos específicos.

O relatório apresenta dados detalhados dos candidatos, vagas e empresas relacionadas às candidaturas.

---

## URL
/relatorio-candidatos

---

# Filtros

| Campo | Tipo | Obrigatório |
|------|------|------|
| Data Início | date | não |
| Data Fim | date | não |
| Cargo / Posição | múltipla seleção | não |

---

## Cargo / Posição

Campo de seleção múltipla que permite escolher um ou mais cargos para filtrar o relatório.

(no admin não está consolidado "ajudante geral" como uma posição única, está tudo separado. por ex. ajudante geral - COZINHA; ajudante geral - SALÃO; ajudante geral - BAR

a idéia é consolidar tudo, no admin está errado)

Exemplo de opções:

- Administrativo - ADM
- Ajudante Geral - COZINHA


Também existe a opção **Select All** para selecionar todos os cargos disponíveis.

---

# Ações

Filtrar  
Aplica os filtros selecionados e atualiza o relatório.

Exportar  
Exporta os dados do relatório para arquivo xlsx.

---

# Campos da Tabela

| Campo | Tipo |
|------|------|
| Candidato | texto |
| Telefone | texto |
| Data da Candidatura | datetime |
| Cargo | texto |
| Área | texto |
| Empresa | texto |
| Cidade | texto |
| UF | texto |
| Cadastro do Candidato | date |
| Data de Criação da Vaga | date |

---

# Fluxo

Administrador acessa:

/relatorio-candidatos

↓

Sistema exibe a tela de relatório com filtros disponíveis.

↓

Administrador seleciona:

- período inicial
- período final
- cargos ou posições

↓

Administrador clica em **Filtrar**.

↓

Sistema retorna os registros de candidaturas que atendem aos filtros.

↓

Administrador pode:

- visualizar os dados diretamente na tabela
- exportar o relatório

---

# Exportação de dados

Ao clicar em **Exportar**, o sistema gera um arquivo contendo as informações do relatório filtrado.

O arquivo contém:

- dados do candidato
- dados da vaga
- dados da empresa
- datas relacionadas à candidatura

---

# API

GET /reports/candidates

Retorna o relatório de candidaturas com base nos filtros aplicados.

---

## Query Params

| Parâmetro | Tipo | Descrição |
|------|------|------|
| start_date | date | Data inicial do filtro |
| end_date | date | Data final do filtro |
| positions | array | Lista de cargos selecionados |

---

## Exemplo de requisição
GET /reports/candidates?start_date=2026-03-01&end_date=2026-03-26&positions=cozinheiro,garcom

---

## Exportação
GET /reports/candidates/export