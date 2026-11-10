# Guia de Publicação: Portal SSMA BAVGRU (PWA no Celular & SharePoint)

Este guia explica como transformar os arquivos em um link seguro (`https://`) e colocá-lo no SharePoint da Vibra como atalho.

---

## 📱 1. Por que transformar em PWA (Progressive Web App)?
O projeto já está configurado com `manifest.json`, `sw.js` (Service Worker) e meta tags mobile.
Quando os operadores e técnicos abrem o link no celular ou tablet:
- **No Android (Chrome/Edge):** Aparece o botão **"Instalar Aplicativo"** automaticamente ou pelo menu de 3 pontinhos.
- **No iPhone/iPad (Safari):** Basta clicar em **Compartilhar (⎋)** e selecionar **"Adicionar à Tela de Início (+)"**.
- **Resultado:** O ícone fica na tela de início do celular com o logo da Vibra SSMA, abrindo em tela cheia (sem barra de endereço do navegador), rápido e com funcionamento até sem sinal de internet (offline).

> **Atenção:** A câmera (captura de foto) e a instalação do aplicativo **exigem um link com HTTPS** (seguro).

---

## 🌐 2. Como publicar e gerar o link HTTPS (3 Opções Práticas)

### Opção A: Vercel ou Netlify (Mais fácil e rápido - 1 minuto, 100% gratuito)
1. Acesse [vercel.com](https://vercel.com) ou [netlify.com](https://netlify.com).
2. Crie uma conta gratuita com seu e-mail ou GitHub.
3. Arraste a pasta `portal-ssma-bavgru` diretamente para a tela de **Deploy / Drop**.
4. Em menos de 20 segundos, o sistema gera um link oficial com cadeado verde (HTTPS), como:
   `https://ssma-bavgru.vercel.app` ou `https://ssma-bavgru.netlify.app`.

---

### Opção B: GitHub Pages (Gratuito e ilimitado)
1. Crie um repositório no GitHub (ex: `ssma-bavgru`).
2. Faça o upload dos 4 arquivos (`index.html`, `manifest.json`, `sw.js`, `icon.svg`).
3. Vá em **Settings > Pages** e em *Branch* selecione `main` e salve.
4. Seu link HTTPS será gerado: `https://seu-usuario.github.io/ssma-bavgru/`.

---

### Opção C: Diretamente no Microsoft 365 / Azure da Vibra (Ambiente Corporativo)
Se a política de TI da Vibra exigir hospedagem interna:
1. **Azure Static Web Apps**: A equipe de TI/TI Industrial pode publicar a pasta no Azure da Vibra com 1 clique (gratuito e integrado ao Azure AD).
2. **Biblioteca de Documentos do SharePoint**:
   - Faça upload da pasta ou do arquivo `index.html` (renomeado para `index.aspx` se o SharePoint da organização permitir execução de scripts).
   - *Nota:* A opção A ou B externa costuma ser a mais ágil para celulares pessoais ou tablets da base sem restrição de VPN.

---

## 📌 3. Como colocar o Atalho no SharePoint da Vibra

Após obter o link (ex: `https://ssma-bavgru.vercel.app`):

### Método 1: Adicionar no Menu Lateral/Superior do SharePoint (Início Rápido)
1. Acesse o site do SharePoint da sua equipe / BAVGRU.
2. No menu esquerdo ou superior, clique em **"Editar"** (ao final da lista de links).
3. Clique no **"+" (Adicionar link)**.
4. Preencha:
   - **Tipo:** Link
   - **Endereço:** Cole o link do seu app (ex: `https://ssma-bavgru.vercel.app`).
   - **Nome de exibição:** `🦺 Portal SSMA - EPIs & Trava-Quedas`
5. Clique em **Salvar**.

---

### Método 2: Criar um Card de Acesso Rápido na Página Inicial (Web Part de Links Rápidos)
1. Abra a página inicial do SharePoint e clique em **Editar** no canto superior direito.
2. Passe o mouse onde deseja colocar e clique em **+ (Adicionar uma nova web part)**.
3. Escolha **"Links Rápidos"** (Quick Links) ou **"Hero" (Destaque)**.
4. Clique em **"Adicionar link"** e cole a URL do seu aplicativo.
5. Personalize:
   - Título: `Portal de Gestão de EPIs & Inspeção SPIQ`
   - Ícone: Escolha um capacete ou escudo de proteção.
   - Descrição: `Dispensação NR-06, Inspeção Anexo C e Auditoria BAVGRU`.
6. Clique em **Publicar / Salvar**.

---

### Método 3: Embutir o aplicativo dentro de uma página do SharePoint (iFrame)
Se você quiser que o portal abra diretamente dentro do SharePoint sem sair dele:
1. No SharePoint, clique em **Editar página**.
2. Adicione a Web Part **"Inserção" (Embed)**.
3. Cole o seguinte código:
```html
<iframe src="https://SEU-LINK-AQUI.vercel.app" width="100%" height="800px" frameborder="0" allow="camera; microphone; display-capture"></iframe>
```
*(Importante: `allow="camera"` garante que o SharePoint permita que o operador tire foto no celular).*

---

## 📲 4. Dica de Ouro para a Base BAVGRU: QR Code no Mural
Gere um QR Code gratuito (no site [qr-code-generator.com](https://www.qr-code-generator.com/) ou no navegador Edge/Chrome clicando com botão direito > "Criar código QR para esta página").

Imprima e cole:
1. Na sala de SSMA / Entrega de EPIs.
2. Próximo aos armários de trava-quedas e talabartes.
3. Na sala de briefing operacional.

Qualquer operador ou técnico aponta a câmera do celular ou tablet para o QR Code, abre o sistema instantaneamente e toca em **"Instalar Aplicativo"**!
