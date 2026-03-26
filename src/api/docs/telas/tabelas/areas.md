# Tela: Áreas

## Objetivo
Permitir que o administrador gerencie as áreas de trabalho do site.

Exemplos de áreas cadastradas:
- Bar
- Salão
- Cozinha
- Administrativo

---

## URL
/area

---

## Campos

| Campo | Tipo | Obrigatório |
|------|------|------|
| Name | texto | sim |
| Cor | hex | não |
| Imagem | url | não |

---

## Ações

Add  
Criar nova área.

Edit  
Editar área selecionada.

Delete  
Excluir área selecionada.

---

## Fluxo

Selecionar área  
↓  
Editar ou excluir

Add  
↓  
Criar nova área

---

## API

GET /areas  
POST /areas  
PUT /areas/{id}  
DELETE /areas/{id}