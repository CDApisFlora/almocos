# 📚 Guia Completo: Subir no GitHub + Supabase

## Parte 1️⃣: Configurar Supabase

### Passo 1: Criar Conta no Supabase
1. Acesse [supabase.com](https://supabase.com)
2. Clique em **"Start your project"**
3. Sign up com GitHub (mais fácil)

### Passo 2: Criar Novo Projeto
1. Clique em **"New project"**
2. Escolha uma **Organization** (ou crie uma)
3. Preencha:
   - **Name**: `almocos`
   - **Database Password**: `algo_forte_aqui_123` (guarde bem!)
   - **Region**: `South America (São Paulo) - sa-east-1`
4. Clique em **Create new project** e aguarde ~2 minutos

### Passo 3: Executar o Script SQL
Quando o projeto carregar:
1. Clique em **SQL Editor** (no menu esquerdo)
2. Clique em **New Query**
3. Cole o conteúdo do arquivo `supabase-setup.sql`
4. Clique em **▶ Run** (botão azul)
5. Pronto! Tabela criada ✅

### Passo 4: Pegar as Credenciais

1. Vá em **Project Settings** (engrenagem no canto inferior esquerdo)
2. Clique em **API** no menu esquerdo
3. Você verá:
   ```
   Project URL: https://xxxxxxxxxxxxx.supabase.co
   anon public key: eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...
   ```
4. **Copie ambas** (vamos usar em breve)

### Passo 5: Configurar RLS (Segurança)

Para os dados ficarem públicos mas seguros:

1. Vá em **Authentication** → **Policies** (lado esquerdo)
2. Clique em **New Policy**
3. Escolha **For INSERT**, depois **Create a policy**
4. Deixe como está (público) e **Review**
5. Repita para **SELECT** e **DELETE**

*Ou execute o script SQL que já faz tudo isso!*

---

## Parte 2️⃣: Configurar GitHub

### Passo 1: Criar Repositório

1. Acesse [github.com](https://github.com)
2. Clique em **➕ New** (ou vá para [github.com/new](https://github.com/new))
3. Preencha:
   - **Repository name**: `almocos`
   - **Description**: `🍽️ App para controle de almoço`
   - **Public** (importante!)
   - **Add a README file** (opcional)
4. Clique em **Create repository**

### Passo 2: Editar o HTML com suas Credenciais

1. Abra o arquivo `almoço-app.html` em um editor de texto
2. Procure por estas linhas (perto do final):
   ```javascript
   const SUPABASE_URL = 'https://seu-projeto.supabase.co';
   const SUPABASE_KEY = 'sua-chave-publica-aqui';
   ```
3. **Substitua** por suas credenciais do Supabase:
   ```javascript
   const SUPABASE_URL = 'https://xxxxxxxxxxxxx.supabase.co';
   const SUPABASE_KEY = 'eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...';
   ```
4. **Salve o arquivo**

### Passo 3: Upload para GitHub (Jeito Fácil)

1. Na página do repositório, clique em **Add file** → **Upload files**
2. Arraste os arquivos:
   - `almoço-app.html` ⭐ (o principal)
   - `README.md`
   - `supabase-setup.sql`
   - `.gitignore`
3. Clique em **Commit changes**

### Passo 4: Ativar GitHub Pages

1. Vá para **Settings** (aba no topo)
2. Clique em **Pages** (menu esquerdo)
3. Em **Branch**:
   - Selecione `main`
   - Selecione `/root` (pasta raiz)
4. Clique em **Save**
5. Aguarde ~1 minuto

Você vai ver:
```
Your site is live at: https://seu-usuario.github.io/almocos/
```

### Passo 5: Acessar o App

Seu app estará em:
```
https://seu-usuario.github.io/almocos/almoço-app.html
```

**Adicione aos favoritos! 🌟**

---

## Parte 3️⃣: (Opcional) Usar Git via Terminal

Se você gosta de terminal:

```bash
# Clonar repositório
git clone https://github.com/seu-usuario/almocos.git
cd almocos

# Editar o almoço-app.html com suas credenciais
# (use seu editor favorito)

# Enviar para GitHub
git add .
git commit -m "Primeira versão: App de almoço com Supabase"
git push origin main
```

---

## 🎉 Pronto!

Seu app está no ar! Agora você pode:

✅ **Compartilhar o link** com seu time  
✅ **Clica em "+ Adicionar"** para adicionar pessoas  
✅ **Clica em "📋 Copiar Imagem"** para copiar no WhatsApp  
✅ **Ver dados sincronizados** em tempo real entre todos

---

## 🆘 Problemas Comuns?

### "Vejo página em branco"
- Verifique o console (F12 → Console)
- Certifique-se de ter editado as credenciais do Supabase

### "Botão 'Copiar Imagem' não funciona"
- Compatibilidade: tente outro navegador
- Ou salve a imagem manualmente

### "Dados não sincronizam"
- Cheque se as credenciais estão certas
- Verifique o Supabase está online
- Dados ainda estarão salvos localmente

### "403 Forbidden no Supabase"
- Provavelmente falta ativar RLS ou as policies estão bloqueando
- Execute o script SQL de setup

---

## 📞 Precisa de Ajuda?

1. Verifique o [README.md](README.md) principal
2. Veja a aba **Issues** do repositório
3. Crie uma issue descrevendo seu problema

Boa sorte! 🚀
