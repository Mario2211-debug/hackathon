# MeetEasy 📅

![Bytes4Future](https://img.shields.io/badge/Bytes4Future-Junior%20Fullstack%20Developer-00b894?style=flat-square)

Sistema completo de gerenciamento de reuniões com interface moderna, minimalista e intuitiva. Gerencie participantes, crie grupos, agende reuniões e visualize tudo em um calendário interativo.

![Next.js](https://img.shields.io/badge/Next.js-16.0-black)
![React](https://img.shields.io/badge/React-19.0-blue)
![Express](https://img.shields.io/badge/Express-5.1-green)
![MongoDB](https://img.shields.io/badge/MongoDB-6.20-green)
![TailwindCSS](https://img.shields.io/badge/TailwindCSS-4.0-38bdf8)

## ✨ Características

- 🎨 **Interface Moderna**: Design minimalista com espaços em branco e cores bem contrastadas
- 📅 **Calendário Interativo**: Visualize reuniões com hover tooltips mostrando detalhes
- 👥 **Sistema de Grupos**: Crie grupos de participantes para facilitar o agendamento
- 🔔 **Notificações**: Email e Telegram para convites de reuniões
- 🌙 **Modo Escuro**: Suporte completo a tema claro/escuro
- 📱 **Responsivo**: Funciona perfeitamente em desktop, tablet e mobile
- 🔐 **Autenticação**: Sistema seguro de login e registro
- 📊 **Dashboard**: Estatísticas e visão geral das reuniões

## 🚀 Tecnologias

### Frontend
- **Next.js 16.0** - Framework React
- **React 19.0** - Biblioteca UI
- **TailwindCSS 4.0** - Estilização
- **Lucide React** - Ícones
- **Context API** - Gerenciamento de estado

### Backend
- **Express 5.1** - Framework Node.js
- **MongoDB** - Banco de dados
- **Mongoose 8.19** - ODM para MongoDB
- **Nodemailer** - Envio de emails
- **Axios** - Cliente HTTP

## 📋 Pré-requisitos

- Node.js 18+ 
- MongoDB (local ou Atlas)
- npm ou yarn

## 🛠️ Instalação

1. **Clone o repositório**
```bash
git clone <repository-url>
cd hackathon
```

2. **Instale as dependências**
```bash
npm install
```

3. **Configure as variáveis de ambiente**

Crie um arquivo `.env` na raiz do projeto:

```env
# MongoDB
MONGODB_URI=mongodb://localhost:27017/meeteasy
# ou para MongoDB Atlas:
# MONGODB_URI=mongodb+srv://usuario:senha@cluster.mongodb.net/meeteasy

# Email (SMTP)
SMTP_HOST=smtp.gmail.com
SMTP_PORT=587
SMTP_USER=seu-email@gmail.com
SMTP_PASS=sua-senha-app
FROM_EMAIL=seu-email@gmail.com
FROM_NAME=MeetEasy

# Telegram (opcional)
TELEGRAM_BOT_TOKEN=seu-token-bot

# Porta do servidor
PORT=3000
```

4. **Execute o seed (opcional)**

Para popular o banco com dados de exemplo:

```bash
node seed.js
```

5. **Inicie o servidor de desenvolvimento**

```bash
npm run dev
```

O servidor estará disponível em `http://localhost:3000`

## 📁 Estrutura do Projeto

```
hackathon/
├── backend/
│   ├── controllers/      # Lógica de negócio
│   │   ├── authController.js
│   │   ├── meetingController.js
│   │   └── groupController.js
│   ├── models/          # Modelos MongoDB
│   │   ├── User.js
│   │   ├── Meeting.js
│   │   └── Group.js
│   ├── routes/          # Rotas da API
│   │   └── index.js
│   ├── lib/            # Bibliotecas
│   │   └── mongodb.js
│   └── utils/          # Utilitários
│       └── notify.js
├── components/          # Componentes React
│   ├── Calendar.jsx
│   ├── Modal.jsx
│   ├── Sidebar.jsx
│   ├── Table.jsx
│   ├── Topbar.jsx
│   └── ToastProvider.jsx
├── pages/               # Páginas Next.js
│   ├── Dashboard.jsx
│   ├── login.jsx
│   ├── register.jsx
│   ├── meetings/
│   └── participants/
├── services/            # Serviços de API
│   └── api.js
├── context/            # Contextos React
│   ├── AuthContext.jsx
│   └── ThemeContext.jsx
├── styles/             # Estilos globais
│   └── globals.css
├── server.js           # Servidor Express + Next.js
└── package.json
```

## 🎯 Funcionalidades

### Autenticação
- ✅ Registro de novos usuários
- ✅ Login seguro
- ✅ Proteção de rotas
- ✅ Gerenciamento de sessão

### Reuniões
- ✅ Criar reuniões com título, data e horário
- ✅ Adicionar participantes manualmente
- ✅ Adicionar grupos inteiros de uma vez
- ✅ Visualizar todas as reuniões em tabela
- ✅ Status de reuniões (Pendente, Confirmada, Cancelada)
- ✅ Resposta de participantes (aceitar/recusar)

### Participantes
- ✅ Cadastro de novos participantes
- ✅ Listagem de todos os participantes
- ✅ Edição e remoção (via detalhes)

### Grupos
- ✅ Criar grupos de participantes
- ✅ Adicionar/remover membros dos grupos
- ✅ Usar grupos ao criar reuniões
- ✅ Visualizar grupos criados

### Dashboard
- ✅ Estatísticas de reuniões
- ✅ Calendário interativo com hover
- ✅ Lista de próximas reuniões
- ✅ Cards informativos

### Calendário Interativo
- ✅ Navegação entre meses
- ✅ Indicadores visuais para dias com reuniões
- ✅ Tooltip com detalhes ao hover
- ✅ Destaque para o dia atual
- ✅ Visualização de participantes nas reuniões

## 🔌 API Endpoints

### Autenticação
```
POST   /api/auth/login          - Login de usuário
POST   /api/auth/register        - Registro de novo usuário
```

### Usuários
```
GET    /api/users                - Listar todos os usuários
```

### Reuniões
```
GET    /api/meetings             - Listar todas as reuniões
POST   /api/meeting               - Criar nova reunião
GET    /api/meetings/respond/:meetingId/:userId - Responder convite
```

### Grupos
```
GET    /api/groups                - Listar todos os grupos
POST   /api/groups                - Criar novo grupo
PUT    /api/groups/:groupId       - Atualizar grupo
DELETE /api/groups/:groupId       - Deletar grupo
```

## 🎨 Design System

### Cores
- **Primária**: Azul (#2563eb / #3b82f6)
- **Sucesso**: Verde (#10b981)
- **Aviso**: Amarelo (#f59e0b)
- **Erro**: Vermelho (#ef4444)
- **Neutro**: Cinza (escala completa)

### Componentes
- **Cards**: Bordas arredondadas, sombras suaves
- **Botões**: Estados hover, disabled, loading
- **Inputs**: Focus states claros, validação visual
- **Modais**: Backdrop blur, animações suaves
- **Tabelas**: Hover states, separadores visuais

## 📱 Responsividade

- **Desktop**: Layout completo com sidebar fixa
- **Tablet**: Sidebar adaptável
- **Mobile**: Sidebar colapsável, layout otimizado

## 🌙 Modo Escuro

O sistema suporta tema claro e escuro automaticamente:
- Cores adaptadas para ambos os temas
- Contraste adequado para acessibilidade
- Transições suaves entre temas
- Preferência do usuário salva

## 🚀 Scripts Disponíveis

```bash
# Desenvolvimento
npm run dev          # Inicia servidor com hot-reload

# Produção
npm run build        # Build do Next.js
npm start            # Inicia servidor de produção

# Seed
node seed.js         # Popula banco com dados de exemplo
```

## 📝 Variáveis de Ambiente

| Variável | Descrição | Obrigatório |
|----------|-----------|-------------|
| `MONGODB_URI` | URI de conexão MongoDB | ✅ Sim |
| `SMTP_HOST` | Host SMTP para emails | ✅ Sim |
| `SMTP_PORT` | Porta SMTP | ✅ Sim |
| `SMTP_USER` | Usuário SMTP | ✅ Sim |
| `SMTP_PASS` | Senha SMTP | ✅ Sim |
| `FROM_EMAIL` | Email remetente | ✅ Sim |
| `FROM_NAME` | Nome remetente | ✅ Sim |
| `TELEGRAM_BOT_TOKEN` | Token do bot Telegram | ❌ Opcional |
| `PORT` | Porta do servidor | ❌ Não (padrão: 3000) |

## 🧪 Testando

### Criar uma reunião
1. Faça login no sistema
2. Vá em "Meetings"
3. Clique em "Nova Reunião"
4. Preencha os dados e adicione participantes
5. Clique em "Criar Reunião"

### Criar um grupo
1. Vá em "Participants"
2. Clique em "Novo Grupo"
3. Preencha o nome e selecione membros
4. Clique em "Criar Grupo"

### Usar grupo em reunião
1. Ao criar uma reunião, selecione um grupo no dropdown
2. Todos os membros do grupo serão adicionados automaticamente
3. Você pode adicionar/remover participantes individualmente

## 🐛 Troubleshooting

### Erro de conexão MongoDB
- Verifique se o MongoDB está rodando
- Confirme a URI no `.env`
- Verifique permissões de acesso

### Emails não sendo enviados
- Verifique credenciais SMTP no `.env`
- Para Gmail, use "Senha de App" (não a senha normal)
- Verifique firewall/portas

### Erro ao iniciar servidor
- Verifique se todas as dependências foram instaladas
- Confirme Node.js 18+
- Verifique logs de erro no console

## 📄 Licença

Este projeto está sob a licença MIT.

## 👥 Contribuindo

Contribuições são bem-vindas! Sinta-se à vontade para:
1. Fazer fork do projeto
2. Criar uma branch para sua feature (`git checkout -b feature/AmazingFeature`)
3. Commit suas mudanças (`git commit -m 'Add some AmazingFeature'`)
4. Push para a branch (`git push origin feature/AmazingFeature`)
5. Abrir um Pull Request

## 📧 Suporte

Para questões ou sugestões, abra uma issue no repositório.

---

Desenvolvido com ❤️ usando Next.js, Express e MongoDB
