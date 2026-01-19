# 🚀 Guia de Deployment - Falciforme+

Este guia explica como publicar o Falciforme+ em diferentes plataformas.

## 📦 Conteúdo do Projeto

Certifique-se que tem estes ficheiros:
```
falciforme-plus/
├── index.html
├── app-anemia-falciforme.html
├── app-profissional-saude.html
├── README.md
├── LICENSE
└── .gitignore
```

---

## 🌐 Opção 1: GitHub Pages (Recomendado)

### Vantagens
- ✅ Grátis
- ✅ HTTPS automático
- ✅ Fácil de configurar
- ✅ Atualizações automáticas

### Passo a Passo

#### 1. Criar Repositório no GitHub

1. Aceda a [github.com](https://github.com)
2. Clique em **"New repository"**
3. Preencha:
   - **Repository name**: `falciforme-plus` (ou outro nome)
   - **Description**: "Sistema de gestão para Anemia Falciforme"
   - **Public** (para usar GitHub Pages grátis)
4. Clique em **"Create repository"**

#### 2. Upload dos Ficheiros

**Opção A: Via Interface Web**
1. No repositório criado, clique em **"uploading an existing file"**
2. Arraste todos os ficheiros do projeto
3. Escreva commit message: "Initial commit"
4. Clique em **"Commit changes"**

**Opção B: Via Git (recomendado)**
```bash
# No terminal, na pasta do projeto
git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin https://github.com/seu-usuario/falciforme-plus.git
git push -u origin main
```

#### 3. Ativar GitHub Pages

1. No repositório, vá a **Settings**
2. No menu lateral, clique em **Pages**
3. Em **Source**, selecione:
   - Branch: `main`
   - Folder: `/ (root)`
4. Clique em **Save**
5. Aguarde 1-2 minutos
6. Aceda ao URL: `https://seu-usuario.github.io/falciforme-plus/`

#### 4. Domínio Personalizado (Opcional)

Se tiver um domínio próprio:
1. Em GitHub Pages > Custom domain, adicione: `www.seudominio.com`
2. No seu registrar de domínios, adicione:
   ```
   CNAME record: www -> seu-usuario.github.io
   ```

---

## 🔥 Opção 2: Netlify

### Vantagens
- ✅ Grátis
- ✅ Deploy contínuo
- ✅ Formulários integrados
- ✅ Redirects fáceis

### Passo a Passo

1. **Criar conta em [netlify.com](https://netlify.com)**

2. **Novo Site**
   - Clique em **"Add new site" > "Deploy manually"**
   - Arraste a pasta do projeto
   - Site publicado instantaneamente!

3. **Ou via Git**
   - Clique em **"Add new site" > "Import from Git"**
   - Conecte ao GitHub
   - Selecione o repositório
   - Deploy automático a cada push!

4. **Domínio Personalizado**
   - Site settings > Domain management
   - Add custom domain

URL: `https://seu-site.netlify.app`

---

## ⚡ Opção 3: Vercel

### Vantagens
- ✅ Grátis
- ✅ Muito rápido
- ✅ Analytics incluído
- ✅ Preview deployments

### Passo a Passo

1. **Criar conta em [vercel.com](https://vercel.com)**

2. **Importar Projeto**
   - Clique em **"Add New Project"**
   - Import do GitHub
   - Selecione o repositório
   - Clique em **Deploy**

3. **Configuração**
   - Framework Preset: **Other**
   - Root Directory: `./`
   - Build Command: (deixe vazio)
   - Output Directory: `./`

URL: `https://seu-projeto.vercel.app`

---

## 🪣 Opção 4: AWS S3 + CloudFront

### Para quem quer mais controlo

1. **Criar bucket S3**
   ```bash
   aws s3 mb s3://falciforme-plus
   ```

2. **Upload ficheiros**
   ```bash
   aws s3 sync . s3://falciforme-plus
   ```

3. **Configurar Static Website Hosting**
   - Ative no bucket S3
   - Index document: `index.html`

4. **CloudFront** (opcional)
   - Para HTTPS e CDN global

---

## 📱 Opção 5: Servidor Próprio

### Apache

1. **Upload via FTP/SFTP**
   - Copie ficheiros para `/var/www/html/`

2. **Configurar .htaccess** (se necessário)
   ```apache
   RewriteEngine On
   RewriteBase /
   ```

### Nginx

1. **Configuração**
   ```nginx
   server {
       listen 80;
       server_name seudominio.com;
       root /var/www/falciforme-plus;
       index index.html;
       
       location / {
           try_files $uri $uri/ =404;
       }
   }
   ```

2. **Restart**
   ```bash
   sudo systemctl restart nginx
   ```

---

## 🔒 HTTPS

### GitHub Pages
- HTTPS automático ✅

### Netlify / Vercel
- HTTPS automático ✅

### Servidor Próprio
Use **Let's Encrypt**:
```bash
sudo certbot --nginx -d seudominio.com
```

---

## 📊 Analytics (Opcional)

### Google Analytics
Adicione antes de `</head>`:
```html
<!-- Google Analytics -->
<script async src="https://www.googletagmanager.com/gtag/js?id=GA_MEASUREMENT_ID"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'GA_MEASUREMENT_ID');
</script>
```

---

## 🔄 Atualizações

### GitHub Pages / Netlify / Vercel
```bash
# Faça alterações
git add .
git commit -m "Atualização X"
git push
# Deploy automático! 🎉
```

### Servidor Próprio
```bash
# Via FTP ou
rsync -avz . usuario@servidor:/var/www/falciforme-plus/
```

---

## ✅ Checklist Pré-Deploy

Antes de publicar, verifique:

- [ ] Testei em Chrome, Firefox, Safari
- [ ] Testei em mobile e desktop
- [ ] Todas as funcionalidades funcionam
- [ ] Links internos funcionam
- [ ] LocalStorage funciona
- [ ] Sem erros no console
- [ ] README.md atualizado
- [ ] Credenciais de teste funcionam

---

## 🆘 Problemas Comuns

### Página não carrega
- ✅ Verifique se `index.html` existe
- ✅ Confirme GitHub Pages está ativo
- ✅ Aguarde 2-5 minutos após ativar

### CSS não aparece
- ✅ Verifique caminhos dos ficheiros
- ✅ Cache do browser (Ctrl+Shift+R)

### LocalStorage não funciona
- ✅ HTTPS é necessário em alguns browsers
- ✅ Verifique permissões do browser

---

## 📞 Suporte

Problemas com deployment?
- 📧 Abra um issue no GitHub
- 💬 Consulte a documentação da plataforma
- 🔍 Stack Overflow

---

**Boa sorte com o deployment! 🚀**
