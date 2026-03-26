# Tela: Modelos de Vagas

## Objetivo
Permitir que o administrador crie e gerencie modelos de vagas que poderão ser utilizados pelas empresas na criação de novas vagas.

Os modelos servem como um **template pré-configurado de vaga**, contendo descrição, jornada de trabalho, área, cargo, benefícios e perguntas para candidatos.

---

## URL
/jobmodels

---

## Campos da Tabela

| Campo | Tipo | Obrigatório |
|------|------|------|
| Name | texto | sim |

---

## Campos do Modelo de Vaga

| Campo | Tipo | Obrigatório |
|------|------|------|
| Nome do Modelo de Vaga | texto | sim |
| Título da Vaga | texto | sim |
| Início da Jornada | horário | não |
| Fim da Jornada | horário | não |
| Descrição da Vaga | texto longo | sim |
| Área | select from /area | sim |
| Cargo | select from /position | sim |
| Tipo de Contrato | select from /regimeContrato (não tem endpoint)| sim |
| Salário + Comissão | número | não |
| Benefícios | múltipla escolha select from /benefit| não |
| Pessoa com deficiência | boolean | não |
| Vaga confidencial | boolean | não |
| Perguntas para candidato | lista | não |

---

## Benefícios Disponíveis (from /benefit)

Os benefícios podem ser selecionados individualmente.

- Almoço Local
- Comissão
- Participação nos Lucros
- Plano Odontológico
- Plano de Saúde
- Seguro de Vida
- Vale Refeição
- Vale Transporte

---

## Perguntas para o Candidato

O administrador pode cadastrar perguntas que serão exibidas ao candidato durante a candidatura.

Exemplos:

- Você conferiu o trajeto que precisará percorrer?
- Você tem disponibilidade para início imediato?
- Você tem experiência na área?

É possível:

- adicionar novas perguntas
- remover perguntas existentes

---

## Ações

Add  
Criar um novo modelo de vaga.

Delete  
Excluir um modelo de vaga selecionado.

Salvar Modelo de Vaga  
Salvar ou atualizar as informações do modelo de vaga.

Cancelar  
Cancelar a edição do modelo.

Adicionar Pergunta  
Adicionar uma nova pergunta ao modelo.

Remover Pergunta  
Remover pergunta cadastrada.

---

## Fluxo

Administrador acessa:

/jobmodels

↓  

Sistema exibe a tabela de modelos de vagas.

↓  

Administrador pode:

- criar um novo modelo
- excluir um modelo
- selecionar um modelo para editar

↓  

Ao selecionar um modelo:

Sistema abre o formulário com os dados do modelo de vaga.

↓  

Administrador pode:

- alterar título da vaga
- editar descrição
- definir jornada de trabalho
- selecionar área
- selecionar cargo
- escolher tipo de contrato
- definir salário
- selecionar benefícios
- marcar vaga confidencial
- marcar vaga para pessoa com deficiência
- adicionar perguntas ao candidato

↓  

Administrador salva o modelo.

---

## API

GET /jobmodels  
Retorna a listagem de modelos de vagas.

GET /jobmodels/{id}  
Retorna os detalhes de um modelo de vaga.

POST /jobmodels  
Cria um novo modelo de vaga.

PUT /jobmodels/{id}  
Atualiza um modelo de vaga.

DELETE /jobmodels/{id}  
Remove um modelo de vaga.

---