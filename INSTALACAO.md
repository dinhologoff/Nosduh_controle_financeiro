# 📱 Guia de Instalação - Nosdu PWA

## Pré-requisitos

- Navegador moderno (Chrome, Firefox, Safari, Edge)
- Conexão com internet (primeira vez)
- Espaço em disco (< 2MB)

---

## 🔧 Instalação Local

### Opção 1: Abrir Diretamente
1. Extraia os arquivos do ZIP
2. Abra `index.html` no navegador
3. Siga as instruções de instalação do seu navegador

### Opção 2: Servidor Local (Recomendado)

#### Com Python 3:
```bash
cd /caminho/para/nosdu_pwa
python -m http.server 8000
```
Acesse: `http://localhost:8000`

#### Com Node.js:
```bash
cd /caminho/para/nosdu_pwa
npx http-server -p 8000
```
Acesse: `http://localhost:8000`

#### Com Live Server (VS Code):
1. Instale a extensão "Live Server"
2. Clique com botão direito em `index.html`
3. Selecione "Open with Live Server"

---

## 📲 Instalação por Dispositivo

### 🤖 Android (Chrome)

1. **Abra o app no Chrome**
   - Navegue até o endereço do Nosdu
   - Aguarde carregar completamente

2. **Instale o app**
   - Toque no menu (⋮) no canto superior direito
   - Selecione "Instalar aplicativo"
   - Confirme com "Instalar"

3. **Acesse na tela inicial**
   - O app aparecerá automaticamente
   - Ou procure por "Nosdu" na gaveta de apps

### 🍎 iOS (Safari)

1. **Abra o app no Safari**
   - Navegue até o endereço do Nosdu
   - Aguarde carregar completamente

2. **Adicione à tela inicial**
   - Toque no ícone Compartilhar (↗️)
   - Role para baixo e selecione "Adicionar à Tela Inicial"
   - Nomeie como "Nosdu"
   - Toque em "Adicionar"

3. **Acesse na tela inicial**
   - O app aparecerá com o ícone 💰
   - Toque para abrir

### 💻 Windows/Mac (Chrome/Edge)

1. **Abra o app no navegador**
   - Navegue até o endereço do Nosdu
   - Aguarde carregar completamente

2. **Instale o app**
   - Clique no ícone de instalação (⬇️) na barra de endereço
   - Ou use o menu (⋮) → "Instalar Nosdu"
   - Confirme a instalação

3. **Acesse o app**
   - Abrirá em uma janela separada
   - Atalho criado no menu Iniciar (Windows) ou Launchpad (Mac)

### 🐧 Linux (Chrome/Firefox)

1. **Abra o app no navegador**
   - Navegue até o endereço do Nosdu
   - Aguarde carregar completamente

2. **Instale o app**
   - Chrome: Menu (⋮) → "Instalar Nosdu"
   - Firefox: Menu (☰) → "Instalar Nosdu"

3. **Acesse o app**
   - Atalho criado no menu de aplicativos
   - Ou procure por "Nosdu" no launcher

---

## 🌐 Hospedagem Online

### Com GitHub Pages (Gratuito)

1. **Crie um repositório**
   ```bash
   git init
   git add .
   git commit -m "Nosdu PWA"
   git branch -M main
   git remote add origin https://github.com/seu-usuario/nosdu.git
   git push -u origin main
   ```

2. **Ative GitHub Pages**
   - Vá para Settings → Pages
   - Source: main branch
   - Salve

3. **Acesse**
   - `https://seu-usuario.github.io/nosdu`

### Com Vercel (Gratuito)

1. **Faça upload**
   - Vá para vercel.com
   - Clique em "New Project"
   - Selecione seu repositório Git
   - Deploy automático

2. **Acesse**
   - `https://seu-projeto.vercel.app`

### Com Netlify (Gratuito)

1. **Faça upload**
   - Vá para netlify.com
   - Clique em "New site from Git"
   - Conecte seu repositório
   - Deploy automático

2. **Acesse**
   - `https://seu-projeto.netlify.app`

### Com Servidor Próprio

1. **Copie os arquivos**
   ```bash
   scp -r nosdu_pwa/* usuario@seu-servidor:/var/www/nosdu/
   ```

2. **Configure HTTPS** (obrigatório para PWA)
   ```bash
   # Com Let's Encrypt
   sudo certbot certonly --standalone -d seu-dominio.com
   ```

3. **Configure Nginx/Apache**
   ```nginx
   server {
       listen 443 ssl http2;
       server_name seu-dominio.com;
       
       ssl_certificate /etc/letsencrypt/live/seu-dominio.com/fullchain.pem;
       ssl_certificate_key /etc/letsencrypt/live/seu-dominio.com/privkey.pem;
       
       root /var/www/nosdu;
       index index.html;
       
       location / {
           try_files $uri $uri/ =404;
       }
   }
   ```

4. **Acesse**
   - `https://seu-dominio.com`

---

## ✅ Verificação de Instalação

### Confirme que o PWA está funcionando:

1. **Abra o DevTools** (F12)
2. **Vá para Application**
3. **Verifique:**
   - ✅ Manifest carregado
   - ✅ Service Worker ativo
   - ✅ Ícones presentes
   - ✅ Cache preenchido

### Teste o Modo Offline:

1. **Abra DevTools** (F12)
2. **Vá para Network**
3. **Marque "Offline"**
4. **Recarregue a página**
5. ✅ O app deve funcionar normalmente

---

## 🔄 Atualizar o App

### Limpar Cache e Atualizar

1. **Abra DevTools** (F12)
2. **Vá para Application → Service Workers**
3. **Clique em "Unregister"**
4. **Recarregue a página** (Ctrl+Shift+R)
5. **Reinstale o app**

### Atualizar Automaticamente

O Service Worker verifica atualizações automaticamente:
- Primeira visita: Baixa todos os arquivos
- Visitas seguintes: Usa cache
- Atualizações: Detectadas automaticamente

---

## 🐛 Solução de Problemas

### "App não instala"
- ✅ Verifique se está usando HTTPS
- ✅ Limpe cache do navegador
- ✅ Tente em navegador diferente
- ✅ Aguarde 30 segundos após carregar

### "Dados não salvam"
- ✅ Verifique se tem espaço em disco
- ✅ Permita armazenamento local
- ✅ Abra DevTools → Console para erros
- ✅ Tente em navegador diferente

### "App fica lento"
- ✅ Limpe dados do navegador
- ✅ Exporte backup e zere dados
- ✅ Reimporte backup
- ✅ Reinstale o app

### "Splash screen não desaparece"
- ✅ Recarregue a página
- ✅ Limpe cache (Ctrl+Shift+Delete)
- ✅ Abra DevTools → Console
- ✅ Procure por mensagens de erro

### "Service Worker não registra"
- ✅ Verifique se está em HTTPS
- ✅ Verifique arquivo `service-worker.js`
- ✅ Abra DevTools → Application → Service Workers
- ✅ Veja erros no console

---

## 📞 Suporte

Se encontrar problemas:

1. **Abra DevTools** (F12)
2. **Vá para Console**
3. **Procure por mensagens de erro**
4. **Anote a mensagem de erro**
5. **Tente solução correspondente acima**

---

## 📋 Checklist de Instalação

- [ ] Arquivos extraídos corretamente
- [ ] Servidor rodando (se local)
- [ ] App carrega sem erros
- [ ] Splash screen aparece
- [ ] App instala no navegador
- [ ] App aparece na tela inicial
- [ ] App funciona offline
- [ ] Dados salvam corretamente
- [ ] Backup funciona
- [ ] Restauração funciona

---

**Pronto!** 🎉 Seu Nosdu PWA está instalado e funcionando!
