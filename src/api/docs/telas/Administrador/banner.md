# Tela: Banner

## Objetivo
Permitir que o administrador gerencie o banner exibido no site do SeuChef, podendo configurar versões específicas para **Desktop** e **Mobile**.

O banner pode ser ativado ou desativado e permite o envio de imagens diferentes para cada tipo de dispositivo.

---

## URL
/banner

---

# Campos

| Campo | Tipo | Obrigatório |
|------|------|------|
| Nome de Identificação | texto | sim |
| Banner Visível no site | boolean | não |
| Banner Desktop | imagem | não |
| Banner Mobile | imagem | não |

---

# Dimensões dos Banners

## Banner Desktop (PC)

Dimensão obrigatória:

1920 x 68 px

Esse banner será exibido para usuários acessando o site através de **computadores ou telas maiores**.

---

## Banner Mobile (Celular)

Dimensão obrigatória:

960 x 68 px


Esse banner será exibido para usuários acessando o site através de **dispositivos móveis**.

---

# Ações

Selecionar Imagem Desktop  
Permite enviar ou substituir a imagem do banner para desktop.

Selecionar Imagem Mobile  
Permite enviar ou substituir a imagem do banner para mobile.

Banner Visível no site  
Ativa ou desativa a exibição do banner no site.

Salvar Alterações  
Salva as configurações realizadas.

---

# Fluxo

Administrador acessa:

/banner

↓

Sistema exibe o formulário de configuração do banner.

↓

Administrador pode:

- definir um nome de identificação
- ativar ou desativar o banner
- enviar imagem para desktop
- enviar imagem para mobile

↓

Administrador clica em **Salvar Alterações**.

↓

Sistema atualiza o banner exibido no site.

---

# API

GET /banner  
Retorna as configurações atuais do banner.

PUT /banner  
Atualiza as configurações do banner.

---

## Body esperado

'''json
{
  "name": "Consumidor",
  "visible": true,
  "desktop_image": "banner-desktop.png",
  "mobile_image": "banner-mobile.png"
}

### Observações
O banner desktop deve respeitar a dimensão 1920x68 px.
O banner mobile deve respeitar a dimensão 960x68 px.
Imagens fora desse padrão podem gerar distorção na exibição do site.