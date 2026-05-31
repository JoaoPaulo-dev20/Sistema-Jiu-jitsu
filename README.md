#  Sistema de Controle — Academia de Jiu-Jitsu

![Status](https://img.shields.io/badge/status-em%20desenvolvimento-yellow)
![Node](https://img.shields.io/badge/Node.js-20.x-339933?logo=node.js&logoColor=white)
![React](https://img.shields.io/badge/React-18.x-61DAFB?logo=react&logoColor=black)
![Supabase](https://img.shields.io/badge/Supabase-PostgreSQL-3ECF8E?logo=supabase&logoColor=white)
![License](https://img.shields.io/badge/licença-acadêmica-blue)

> Projeto acadêmico de desenvolvimento web — sistema para gerenciamento de alunos, presenças e pagamentos de uma academia de jiu-jitsu, com reconhecimento facial automatizado.

---

##  Índice

- [Sobre o Projeto](#sobre-o-projeto)
- [Funcionalidades](#funcionalidades)
- [Tecnologias](#tecnologias)
- [Estrutura do Projeto](#estrutura-do-projeto)
- [Como Rodar](#como-rodar)
- [Variáveis de Ambiente](#variáveis-de-ambiente)
- [Roadmap](#roadmap)
- [Documentação](#documentação)
- [Autor](#autor)

---

## Sobre o Projeto

Sistema web desenvolvido para centralizar a gestão de uma academia de jiu-jitsu, substituindo processos manuais (planilhas, cadernos, WhatsApp) por uma plataforma digital integrada.

O sistema permite que o professor/administrador controle a frequência dos alunos — inclusive via reconhecimento facial em fotos da turma —, gerencie mensalidades e acompanhe o histórico completo de cada aluno.

---

## Funcionalidades

###  Módulo de Alunos
- Cadastro completo com foto, faixa e dados de contato
- Listagem, busca e edição de alunos
- Inativação e reativação de cadastros

###  Módulo de Presença
- Chamada manual por lista de alunos
- Chamada automática via reconhecimento facial em foto da turma
- Histórico e relatório de frequência por aluno

###  Módulo Financeiro
- Controle de mensalidades por aluno
- Status de pagamento (pago, pendente, em atraso)
- Alertas de inadimplência e histórico financeiro

###  Módulo de Relatórios
- Dashboard com visão geral do mês
- Frequência percentual por aluno e período
- Exportação de relatórios

---

## Tecnologias

| Camada | Tecnologia |
|--------|-----------|
| Frontend | React 18 + Vite |
| Estilização | Tailwind CSS |
| Backend | Node.js + Express |
| Banco de dados | PostgreSQL via Supabase |
| Autenticação | JWT + Supabase Auth |
| Upload de arquivos | Multer |
| Reconhecimento facial | face-api.js *(Fase 4)* |

---

## Estrutura do Projeto

```
jiu-jitsu-system/
├── backend/
│   ├── src/
│   │   ├── controllers/      # Lógica de cada rota
│   │   ├── routes/           # Definição das rotas da API
│   │   ├── middlewares/      # Autenticação JWT e validações
│   │   ├── services/         # Regras de negócio
│   │   ├── models/           # Modelos e queries do banco
│   │   ├── config/           # Configuração do Supabase
│   │   └── utils/            # Funções auxiliares
│   ├── uploads/              # Arquivos enviados (ignorado pelo Git)
│   ├── .env.example          # Modelo de variáveis de ambiente
│   └── package.json
├── frontend/
│   └── src/
│       ├── components/       # Componentes reutilizáveis
│       ├── pages/            # Páginas da aplicação
│       ├── services/         # Chamadas à API (axios)
│       ├── hooks/            # Custom hooks
│       ├── context/          # Estado global (Context API)
│       └── assets/           # Imagens e ícones
├── docs/                     # Documentação acadêmica
│   ├── requisitos.docx
│   └── diagramas/
└── README.md
```

---

## Como Rodar

### Pré-requisitos

- [Node.js](https://nodejs.org) v18 ou superior
- [Git](https://git-scm.com)
- Conta no [Supabase](https://supabase.com) (gratuita)

### 1. Clone o repositório

```bash
git clone https://github.com/SEU_USUARIO/jiu-jitsu-system.git
cd jiu-jitsu-system
```

### 2. Configure o Backend

```bash
cd backend
npm install
cp .env.example .env
```

Preencha o arquivo `.env` com suas credenciais (veja a seção abaixo).

```bash
npm run dev
```

A API estará disponível em `http://localhost:3001`

### 3. Configure o Frontend

```bash
cd frontend
npm install
npm run dev
```

O frontend estará disponível em `http://localhost:5173`

---

## Variáveis de Ambiente

Crie um arquivo `.env` dentro da pasta `backend/` com base no `.env.example`:

```env
# Supabase
SUPABASE_URL=sua_url_aqui
SUPABASE_KEY=sua_chave_aqui

# JWT
JWT_SECRET=sua_chave_secreta_aqui
JWT_EXPIRES_IN=7d

# Servidor
PORT=3001
NODE_ENV=development
```

>  **Nunca** envie o arquivo `.env` para o GitHub. Ele já está no `.gitignore`.

---

## Roadmap

- [x] Setup inicial do projeto
- [x] Documentação de requisitos (v1.0)
- [ ] **Fase 1** — Cadastro de alunos e autenticação
- [ ] **Fase 2** — Controle de presença manual
- [ ] **Fase 3** — Controle de pagamentos
- [ ] **Fase 4** — Reconhecimento facial
- [ ] **Fase 5** — Dashboard e relatórios

---

## Documentação

A documentação completa do projeto está disponível na pasta [`/docs`](./docs), incluindo:

- Documento de Requisitos Funcionais e Não Funcionais
- Casos de Uso detalhados
- Perguntas de alinhamento com o cliente

---

## Autor

Desenvolvido por **JP**
Orientador: **Prof. Renato**

Projeto acadêmico — 2025