# GUIA — Deploy no Netlify

## Passo 1 — Subir o código no GitHub

```bash
# Na pasta do projeto
git init
git add .
git commit -m "feat: portfólio profissional inicial"
git branch -M main
git remote add origin https://github.com/SEU-USUARIO/portfolio-gilcy.git
git push -u origin main
```

---

## Passo 2 — Conectar ao Netlify

1. Acesse [app.netlify.com](https://app.netlify.com) e faça login (pode usar a conta GitHub)
2. Clique em **"Add new site"** → **"Import an existing project"**
3. Selecione **GitHub** e autorize o acesso
4. Escolha o repositório `portfolio-gilcy`

---

## Passo 3 — Configurar o deploy

Na tela de configuração, preencha:

| Campo | Valor |
|---|---|
| **Branch to deploy** | `main` |
| **Base directory** | *(deixar vazio)* |
| **Build command** | *(deixar vazio)* |
| **Publish directory** | `.` |

Clique em **"Deploy site"**.

---

## Passo 4 — Site no ar! 🟢

Em cerca de 30 segundos o Netlify gera uma URL como:
```
https://nome-aleatorio.netlify.app
```

Para personalizar a URL gratuita:
1. Vá em **Site configuration** → **Site details**
2. Clique em **"Change site name"**
3. Defina um nome (ex: `drgilcykelly` → `drgilcykelly.netlify.app`)

---

## Passo 5 — Atualizações automáticas

A cada `git push`, o Netlify detecta a mudança e republica automaticamente:

```bash
# Edite os arquivos, depois:
git add .
git commit -m "update: atualização do portfólio"
git push
```

O deploy leva ~30 segundos. ✅

---

## Domínio personalizado (opcional)

Se tiver um domínio próprio (ex: `gilcykelly.com.br`):

1. Em **Domain management** → **Add a domain**
2. Digite seu domínio e clique em **"Verify"**
3. Configure o DNS no painel do seu registrador:
   - Tipo: `CNAME`
   - Nome: `www`
   - Valor: `nome-do-site.netlify.app`
4. O Netlify ativa HTTPS automaticamente (Let's Encrypt) 🔒

---

> Desenvolvido por **Green Monster Project** · Dev Erick de Lima Souza
