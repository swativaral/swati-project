# 💰 AI Finance Tracker

> A smart personal finance tracker powered by AI — track expenses, visualize spending, and get intelligent insights.

![License](https://img.shields.io/badge/license-MIT-blue.svg)
![Node](https://img.shields.io/badge/node-%3E%3D18.0.0-brightgreen)
![React](https://img.shields.io/badge/react-18.x-61DAFB)
![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)

---

## 🚀 Features

- 📊 **Dashboard** — Visual breakdown of income vs expenses with charts
- ➕ **Transaction Manager** — Add, edit, delete income/expense entries
- 🤖 **AI Insights** — Ask Claude AI: *"Where am I overspending?"*
- 🎯 **Budget Goals** — Set monthly limits per category with alerts
- 📁 **Export** — Download your data as CSV
- 🔐 **Auth** — JWT-based secure login & registration

---

## 🛠 Tech Stack

| Layer      | Technology                    |
|------------|-------------------------------|
| Frontend   | React 18, Tailwind CSS, Recharts |
| Backend    | Node.js, Express.js           |
| Database   | MongoDB + Mongoose            |
| AI         | Claude API (Anthropic)        |
| Auth       | JWT + bcrypt                  |
| Deployment | Vercel (FE) + Render (BE)     |

---

## 📁 Project Structure

```
finance-tracker/
├── client/                  # React frontend
│   ├── src/
│   │   ├── components/      # Reusable UI components
│   │   │   ├── Navbar.jsx
│   │   │   ├── TransactionCard.jsx
│   │   │   ├── AddTransactionModal.jsx
│   │   │   ├── SpendingChart.jsx
│   │   │   └── AIChat.jsx
│   │   ├── pages/           # Page components
│   │   │   ├── Dashboard.jsx
│   │   │   ├── Transactions.jsx
│   │   │   ├── Login.jsx
│   │   │   └── Register.jsx
│   │   ├── context/
│   │   │   └── AuthContext.jsx
│   │   ├── utils/
│   │   │   └── api.js
│   │   ├── App.jsx
│   │   └── main.jsx
│   ├── index.html
│   ├── package.json
│   └── tailwind.config.js
│
├── server/                  # Express backend
│   ├── routes/
│   │   ├── auth.js
│   │   ├── transactions.js
│   │   └── ai.js
│   ├── models/
│   │   ├── User.js
│   │   └── Transaction.js
│   ├── middleware/
│   │   └── authMiddleware.js
│   ├── server.js
│   └── package.json
│
├── docs/                    # Documentation & assets
│   └── api.md
├── .env.example
├── .gitignore
└── README.md
```

---

## ⚙️ Getting Started

### Prerequisites

- Node.js >= 18
- MongoDB (local or [MongoDB Atlas](https://www.mongodb.com/cloud/atlas))
- Anthropic API key — [get one here](https://console.anthropic.com/)

### 1. Clone the repo

```bash
git clone https://github.com/YOUR_USERNAME/finance-tracker.git
cd finance-tracker
```

### 2. Set up environment variables

```bash
cp .env.example .env
```

Fill in your `.env`:

```env
MONGO_URI=your_mongodb_connection_string
JWT_SECRET=your_super_secret_key
ANTHROPIC_API_KEY=your_anthropic_api_key
PORT=5000
```

### 3. Install & run the backend

```bash
cd server
npm install
npm run dev
```

### 4. Install & run the frontend

```bash
cd client
npm install
npm run dev
```

Visit `http://localhost:5173` 🎉

---

## 🔌 API Endpoints

| Method | Endpoint                   | Description              | Auth |
|--------|----------------------------|--------------------------|------|
| POST   | `/api/auth/register`       | Register new user        | ❌   |
| POST   | `/api/auth/login`          | Login, returns JWT       | ❌   |
| GET    | `/api/transactions`        | Get all transactions     | ✅   |
| POST   | `/api/transactions`        | Add a transaction        | ✅   |
| PUT    | `/api/transactions/:id`    | Update a transaction     | ✅   |
| DELETE | `/api/transactions/:id`    | Delete a transaction     | ✅   |
| POST   | `/api/ai/chat`             | AI financial insight     | ✅   |

See [`docs/api.md`](docs/api.md) for full details.

---

## 🤖 AI Feature

The AI chat uses the **Claude API** to analyze your transaction history and answer natural language questions:

- *"How much did I spend on food this month?"*
- *"Am I on track for my savings goal?"*
- *"What category should I cut back on?"*

Your transaction data is sent (never stored by Anthropic) to generate context-aware responses.

---

## 🚢 Deployment

### Frontend → Vercel

```bash
cd client
npm run build
# Connect repo to vercel.com and set env vars
```

### Backend → Render

1. Push to GitHub
2. Create a new **Web Service** on [render.com](https://render.com)
3. Set root directory to `server/`
4. Add environment variables
5. Deploy!

---

## 🤝 Contributing

Contributions are welcome! Please:

1. Fork the repo
2. Create a branch: `git checkout -b feature/your-feature`
3. Commit: `git commit -m 'Add your feature'`
4. Push: `git push origin feature/your-feature`
5. Open a Pull Request

---

## 📄 License

MIT © [Your Name](https://github.com/YOUR_USERNAME)

---

## 🙏 Acknowledgements

- [Anthropic Claude](https://anthropic.com) for the AI API
- [Recharts](https://recharts.org) for beautiful charts
- [Tailwind CSS](https://tailwindcss.com) for styling
