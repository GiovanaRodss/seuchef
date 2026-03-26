# Tela: Benfícios

## Objetivo
Permitir que o administrador gerencie os benefícios das vagas.

Exemplos de benefícios cadastradas:
- Almoço Local
- Comissão
- Plano de Saúde
- Seguro de vida

---

## URL
/benefit

---

## Campos

| Campo | Tipo | Obrigatório |
|------|------|------|
| Name | texto | sim |

---

## Ações

Add  
Criar novo benefício.

Edit  
Editar benefício selecionado.

Delete  
Excluir benefício selecionado.

---

## Fluxo

Selecionar benefício  
↓  
Editar ou excluir

Add  
↓  
Criar novo benefício

---

## API

GET /benefit  
POST /benefit  
PUT /benefit/{id}  
DELETE /benefit/{id}