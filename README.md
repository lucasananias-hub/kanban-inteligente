# 🏗️ SprintFlow Kanban

Board Kanban ágil com IA generativa (Claude), persistência Supabase e deploy Vercel.

## 🚀 Setup Rápido

### 1️⃣ SUPABASE — Criar banco de dados

1. Acesse [supabase.com](https://supabase.com) → seu projeto
2. Vá em **SQL Editor** (menu lateral)
3. Cole todo o conteúdo de `supabase/schema.sql` e clique **Run**
4. Vá em **Settings → API** e copie:
   - `Project URL` → será `NEXT_PUBLIC_SUPABASE_URL`
   - `anon public key` → será `NEXT_PUBLIC_SUPABASE_ANON_KEY`

### 2️⃣ GITHUB — Subir repositório

```bash
cd sprintflow-kanban
git init
git add .
git commit -m "Initial commit - SprintFlow Kanban"
git branch -M main
git remote add origin https://github.com/SEU_USUARIO/sprintflow-kanban.git
git push -u origin main
```

### 3️⃣ VERCEL — Deploy

1. Acesse [vercel.com](https://vercel.com) → **Add New Project**
2. Importe o repositório `sprintflow-kanban`
3. Em **Environment Variables**, adicione:
   - `NEXT_PUBLIC_SUPABASE_URL` = sua URL do Supabase
   - `NEXT_PUBLIC_SUPABASE_ANON_KEY` = sua anon key
4. Clique **Deploy** ✅

### 4️⃣ Pronto!

Sua URL será algo como: `https://sprintflow-kanban.vercel.app`

## 📁 Estrutura

```
sprintflow-kanban/
├── src/
│   ├── app/
│   │   ├── globals.css
│   │   ├── layout.js
│   │   └── page.js
│   ├── components/
│   │   └── KanbanApp.jsx    ← Componente principal
│   └── lib/
│       └── supabase.js      ← Client Supabase
├── supabase/
│   └── schema.sql           ← SQL para criar tabelas
├── package.json
├── next.config.js
├── tailwind.config.js
└── .env.example
```

## 🗄️ Tabelas Supabase

| Tabela | Descrição |
|--------|-----------|
| `developers` | Time de desenvolvimento |
| `clients` | Clientes/Projetos |
| `cards` | Tasks do Kanban |
| `daily_notes` | Histórico de daily por card |
| `cards_with_notes` | View com notes agregadas |
