# Tela: Escolaridade

## Objetivo
Permitir que o administrador gerencie as escolaridades dos candidatos do site.

Exemplos de escolaridades cadastradas:
- Superior Completo
- Lê e Escreve
- Nenhuma Escolaridade
- Fundamental Completo

---

## URL
/education

---

## Campos

| Campo | Tipo | Obrigatório |
|------|------|------|
| Description | texto | sim |

---

## Ações

Add  
Criar nova escolaridade.

Edit  
Editar escolaridade selecionada.

Delete  
Excluir escolaridade selecionada.

---

## Fluxo

Selecionar escolaridade  
↓  
Editar ou excluir

Add  
↓  
Criar nova escolaridade

---

## API

GET /education 
POST /education  
PUT /education/{id}  
DELETE /education/{id}