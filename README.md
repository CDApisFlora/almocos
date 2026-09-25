# 🍽️ Almoço - App de Controle de Pedidos

Um app simples e prático para gerenciar pedidos de almoço. Feito em HTML puro com Supabase para sincronizar dados.

## ✨ Funcionalidades

- ✅ **Data automática** - Sempre mostra o dia atual
- ✅ **Adicionar/remover pessoas** - Interface simples e rápida
- ✅ **Particularidades** - Anote observações (sem feijão, sem arroz, etc)
- ✅ **Total automático** - Calcula quantas marmitas serão
- ✅ **Copiar para WhatsApp** - Botão que copia a imagem da tabela
- ✅ **Sincronização** - Salva dados no Supabase (com fallback local)
- ✅ **Sem servidor** - Funciona 100% no navegador (GitHub Pages)

## 🚀 Configuração Rápida

### 1. **Criar um projeto no Supabase**

1. Acesse [supabase.com](https://supabase.com)
2. Clique em "New project"
3. Preench os dados:
   - **Project name**: `almocos`
   - **Database password**: Guarde bem (vai precisar)
   - **Region**: `South America (São Paulo)` (mais perto de você)

### 2. **Criar a tabela no Supabase**

Após criar o projeto, vá em **SQL Editor** e execute:

```sql
CREATE TABLE almocos (
  id BIGSERIAL PRIMARY KEY,
  data DATE NOT NULL,
  nome TEXT NOT NULL,
  quantidade INTEGER DEFAULT 1,
  particularidades TEXT,
  created_at TIMESTAMP DEFAULT NOW()
);

-- Índice para buscar por data (mais rápido)
CREATE INDEX idx_almocos_data ON almocos(data);
```

### 3. **Pegar as credenciais**

1. Vá em **Project Settings** → **API**
2. Copie:
   - `Project URL` (vai ser algo como `https://xxxx.supabase.co`)
   - `anon public` key

### 4. **Editar o arquivo HTML**

Abra o arquivo `almoço-app.html` e procure por:

```javascript
const SUPABASE_URL = 'https://seu-projeto.supabase.co';
const SUPABASE_KEY = 'sua-chave-publica-aqui';
```

Cole suas credenciais lá (a URL e a chave).

### 5. **Subir no GitHub Pages**

1. Crie um repositório no GitHub chamado `almocos`
2. Faça upload do arquivo `almoço-app.html`
3. Vá em **Settings** → **Pages**
4. Em **Branch**, selecione `main` e pasta `/root`
5. Seu site ficará em: `https://seu-usuario.github.io/almocos/almoço-app.html`

### 6. **RLS (Row Level Security) - Opcional mas Recomendado**

Para maior segurança, no Supabase vá em **Authentication** → **Policies** e adicione:

```sql
-- Qualquer um pode ler (public)
CREATE POLICY "Enable read access for all users" ON almocos
  FOR SELECT USING (true);

-- Qualquer um pode inserir (public)
CREATE POLICY "Enable insert access for all users" ON almocos
  FOR INSERT WITH CHECK (true);

-- Qualquer um pode deletar seus próprios dados
CREATE POLICY "Enable delete access for all users" ON almocos
  FOR DELETE USING (true);
```

## 🔄 Como Usar

1. **Abra a página** no seu navegador
2. **Clique em "+ Adicionar"** para adicionar uma pessoa
3. **Preencha**:
   - Nome
   - Quantidade de marmitas (default: 1)
   - Particularidades (opcional)
4. **Clique em "Salvar"**
5. **Para compartilhar**: Clique em "📋 Copiar Imagem" e cole no WhatsApp

## 💾 Backup de Dados

Os dados são salvos em dois lugares:
- **Supabase** (nuvem - sincroniza entre dispositivos)
- **LocalStorage** (seu navegador - funciona offline)

Se o Supabase cair, o app continua funcionando localmente.

## 🛠️ Estrutura do Repositório

```
almocos/
├── almoço-app.html          # Aplicativo principal
├── README.md                # Este arquivo
├── .gitignore              # Arquivos a ignorar no git
└── supabase-setup.sql      # Script de configuração do banco
```

## 🐛 Troubleshooting

**"Copiar Imagem" não funciona?**
- Seu navegador pode não suportar clipboard com imagens
- Alternativamente, clique com botão direito e "Salvar imagem"

**Dados não sincronizam?**
- Verifique se as credenciais do Supabase estão certas
- Cheque o console (F12 → Console) para ver erros
- Os dados ainda estarão salvos localmente mesmo assim

**Vejo "Carregando dados..." forever?**
- Provavelmente as credenciais estão inválidas
- Verifique a URL e chave do Supabase

## 📱 Compatibilidade

- ✅ Chrome/Edge
- ✅ Firefox
- ✅ Safari
- ✅ Mobile (funciona bem no celular também!)

## 🔐 Segurança

- Não há login (opcional - avise se quiser adicionar)
- As credenciais do Supabase são públicas (por isso o RLS é importante)
- Os dados são salvos com a data do dia

## 📝 Licença

Livre para usar, modificar e compartilhar!

---

**Dúvidas?** Deixe um comentário ou crie uma issue no repositório.
