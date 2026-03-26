# Tela: Cargos

## Objetivo
Permitir que o administrador gerencie os cargos de trabalho do site.

Exemplos de cargos cadastradas:
- Comprador (a)
- Estoquista
- Gerente RH
- Barman
- Chefe de Bar

---

## URL
/position

---

## Campos

| Campo | Tipo | Obrigatório |
|------|------|------|
| Description | texto | sim |
| area | texto | sim |

---

## Ações

Add  
Criar novo cargo.

Edit  
Editar cargo selecionado.

Delete  
Excluir cargo selecionado.

---

## Fluxo

Selecionar cargo  
↓  
Editar ou excluir

Add  
↓  
Criar novo cargo

---

## API

GET /positions  
POST /positions  
PUT /positions/{id}  
DELETE /positions/{id}