# Tela: Assinaturas

## Objetivo
Permitir que o administrador tenha acesso as empresas que participaram da Assinatura.

Tabela com informações das empresas

## Campos
NOME | CNPJ | DATA ASSOCIAÇÃO | STATUS | ÚLTIMO PAGAMENTO | STATUS | VALOR | RESPONSÁVEL | TELEFONE RESPONSÁVEL

---

## URL
/signs
---

## Ações

### Visualizar detalhes da assinatura

Ao clicar em uma linha da tabela de assinaturas, o sistema abre um **modal de detalhes da empresa**.

Esse modal exibe as seguintes informações:

- Nome da empresa
- CNPJ
- Data da assinatura
- Status da assinatura
- Último pagamento
- Responsável
- Telefone
- Email

Também são exibidos os dados cadastrais da empresa:

- Razão Social
- CNPJ
- Inscrição Estadual
- Endereço
- CEP
- Bairro
- Cidade
- Estado

Além disso, o modal apresenta:

- Código da assinatura
- Referência da assinatura
- Histórico de cobranças
- Status dos pagamentos
- NFs relacionadas

### Ações disponíveis no modal
- **Salvar**
  Salva o número da NF relacionada ao pagamento.

- **Ativar Assinatura (30 dias)**  
  Ativa ou renova a assinatura da empresa por mais 30 dias.

- **Fechar modal**  
  Fecha a visualização de detalhes da assinatura.

---
## Interações da tabela

| Ação do usuário | Resultado |
|----------------|----------|
| Clique em uma linha da assinatura | Abre modal com detalhes da empresa e da assinatura |
| Clique em "Ativar Assinatura" | Ativa a assinatura por 30 dias |
| Clique em "X" | Fecha o modal |

--- 

## Fluxo

Lista de Assinaturas
        ↓
Selecionar Empresa
        ↓
Abrir Modal de Detalhes
        ↓
[ Ver informações ]
        ↓
[ Ativar assinatura ]
        ↓
Fechar modal
        ↓
Voltar para lista

---

## API

### GET /signs

Retorna a listagem paginada de assinaturas.

#### Query params
- page
- per_page
- company_name
- cnpj
- sign_status
- payment_status

#### Response EXEMPLO
```json
{
  "data": [
    {
      "id": 1,
      "company_name": "Piatto Panino",
      "cnpj": "47748219000137",
      "association_date": "2025-01-28 11:02:43",
      "sign_status": "Inativa",
      "last_payment_date": "2025-05-28 07:00:53",
      "payment_status": "Paga",
      "amount": 49.00,
      "responsible_name": "Salvador",
      "responsible_phone": "11915509073"
    }
  ],
  "page": 1,
  "total": 182
}