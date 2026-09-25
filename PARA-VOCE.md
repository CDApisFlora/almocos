# 🍽️ Seu App de Almoço - Passo a Passo Simplificado

Oi Rhuan! Aqui está exatamente o que você pediu. Segue o passo-a-passo:

## 🎯 O que você vai ganhar:

✅ Não precisa mais filtrar/copiar dados da planilha  
✅ Cada dia começa limpo (data automática)  
✅ Um clique pra copiar a imagem e mandar no WhatsApp  
✅ Dados salvos online (Supabase) + local (seu navegador)  
✅ Acessível de qualquer lugar (GitHub Pages)  

---

## ⚡ Quick Start (5 minutos)

### 1. **Criar Supabase** (2 minutos)

Você vai em [supabase.com](https://supabase.com):
- Click "Start your project"
- Sign up com GitHub (da forma que você preferir)
- Novo projeto:
  - Name: `almocos`
  - Password: qualquer senha forte (ex: `123Mudar@Depois`)
  - Region: **São Paulo** (sa-east-1)
  - Create

Vai levar ~2 minutos. Enquanto aguarda, siga para o passo 2.

### 2. **Copiar Credenciais** (1 minuto)

Quando o Supabase terminar de carregar:
- Clique em **Settings** (engrenagem embaixo)
- Clique em **API**
- Você vai ver 2 coisas:
  - `Project URL` (type `https://...supabase.co`)
  - `anon public` (aquela chave gigante)
- **Copie as duas** (você vai colar no HTML)

### 3. **Executar Script SQL** (30 segundos)

- Clique em **SQL Editor**
- Clique em **New Query**
- Abra o arquivo `supabase-setup.sql` (que preparei pra você)
- Copie todo o conteúdo
- Cola no Supabase
- Click **Run** (botão azul)
- ✅ Pronto! Tabela criada

### 4. **Editar HTML com suas Credenciais** (1 minuto)

- Abra `almoço-app.html` em qualquer editor de texto
- Procure por:
  ```javascript
  const SUPABASE_URL = 'https://seu-projeto.supabase.co';
  const SUPABASE_KEY = 'sua-chave-publica-aqui';
  ```
- **Substitua**:
  - URL: Cole o `Project URL` do Supabase
  - KEY: Cole o `anon public` do Supabase
- Salve

### 5. **Subir no GitHub** (1 minuto)

- Vá em [github.com/new](https://github.com/new)
- Name: `almocos`
- **Public** (importante!)
- Create repository
- Clique em **Add file → Upload files**
- Arraste os 4 arquivos:
  - `almoço-app.html` ⭐
  - `README.md`
  - `supabase-setup.sql`
  - `.gitignore`
- Clique **Commit changes**

### 6. **Ativar GitHub Pages** (30 segundos)

- Clique em **Settings** (aba no topo)
- Clique em **Pages** (menu esquerdo)
- **Branch**: selecione `main` e pasta `/root`
- **Save**
- Aguarde 1 minuto

Seu site vai estar em:
```
https://seu-usuario.github.io/almocos/almoço-app.html
```

**Pronto! 🎉**

---

## 🎮 Como Usar o App

1. **Abra o link** que você ganhou acima
2. **Clique "+ Adicionar"**
3. Preencha:
   - Nome (ex: Ariosan)
   - Quantidade (default: 1)
   - Particularidades (ex: Sem feijão)
4. Clique "Salvar"
5. Repita pro pessoal
6. **Pronto pra enviar?** Clique "📋 Copiar Imagem"
7. Cole no WhatsApp! ✅

A data muda automaticamente cada dia.

---

## 📋 Checklist de Configuração

- [ ] Criei conta no Supabase
- [ ] Criei novo projeto no Supabase
- [ ] Executei o script SQL
- [ ] Copiei as credenciais (URL + KEY)
- [ ] Editei o `almoço-app.html` com minhas credenciais
- [ ] Criei repositório no GitHub
- [ ] Upload dos 4 arquivos no GitHub
- [ ] Ativei GitHub Pages
- [ ] Testei a URL (clicando no link)

---

## 🆘 Se Der Errado

**"Vejo página em branco ou 'Carregando dados...'"**
- Abra o Console (F12 → Console)
- Veja se tem algum erro em vermelho
- Provavelmente é a URL ou KEY do Supabase erradas

**"Botão 'Copiar Imagem' não funciona"**
- Alguns navegadores antigos não permitem
- Tente Chrome ou Edge
- Ou clique com botão direito e "Salvar imagem"

**"Dados não estão aparecendo"**
- Verifique se o Supabase está respondendo
- Mesmo assim, dados são salvos localmente no seu navegador
- F12 → Console para ver erros

---

## 💡 Dicas

- **Favoritar a URL** no navegador para acesso rápido
- **Compartilhar a URL** com o time todo (cada um adiciona seu almoço)
- **Diariamente** a lista limpa (começa vazia) e você vai adicionando
- **WhatsApp** - Clone a imagem todo dia e manda pro grupo

---

## 📞 Ficou com dúvida?

Deixa comigo! Posso:
- Explicar cada passo novamente
- Ajudar com Supabase/GitHub
- Melhorar a interface se precisar
- Adicionar mais funcionalidades

É só falar! 😊

---

**Boa sorte com o app! Vai facilitar bastante a rotina do almoço.** 🍽️
