# 🪙 Mini Binance Demo (MVP)

A **Mini Binance MVP** is a simplified, educational cryptocurrency exchange platform inspired by Binance. This project demonstrates **core exchange concepts** such as user authentication, wallet management, order placement, and basic trade matching — designed for **learning, demos, hackathons, and academic projects**.

> ⚠️ **Disclaimer**: This is **NOT a real exchange**. No real money or live blockchain funds should be used.

---

## 📌 1. Problem Statement

Traditional financial systems:

* Are slow and centralized
* Lack transparency
* Have high transaction costs
* Are not accessible globally

Crypto exchanges like Binance solve these problems, but:

* They are complex to understand
* Difficult to replicate for learning

👉 **Goal**: Build a **Mini Binance MVP** that explains and demonstrates how a crypto exchange works internally.

---

## 🎯 2. Solution Overview

The Mini Binance MVP provides:

* User registration & login
* Virtual wallets (INR + Crypto)
* Spot trading (Buy/Sell)
* Order matching (basic)
* Transaction ledger
* Admin monitoring (optional)

All operations are done using **dummy balances**.

---

## 🧠 3. Core Concepts Covered

* Centralized Exchange (CEX)
* Order Book (Buy/Sell)
* Wallet & Ledger System
* Matching Engine (simplified)
* KYC-based access (mock)
* Security basics (JWT, hashing)

---

## 🧩 4. Features (MVP Scope)

### 👤 User Features

* Register / Login
* View wallet balances
* Deposit virtual funds
* Buy / Sell crypto (Spot)
* Transaction history

### ⚙️ System Features

* Order matching engine
* Price calculation
* Balance updates
* Trade execution logic

---

## 🏗️ 5. High-Level System Architecture

```
[ Frontend (React) ]
        |
        v
[ Backend API (Node.js + Express) ]
        |
        v
[ Matching Engine ]
        |
        v
[ Wallet & Ledger ]
        |
        v
[ Database (MongoDB) ]
```

---

## 🔄 6. Technical Workflow

### User Trade Flow

1. User logs in
2. Views wallet balance
3. Places Buy/Sell order
4. Order sent to backend
5. Matching engine checks opposite orders
6. Trade executed
7. Wallet balances updated
8. Transaction stored

---

## 📊 7. Data Flow Diagram (DFD)

### Level 0 DFD

```
User → Frontend → Backend → Database
User ← Frontend ← Backend ← Database
```

### Level 1 DFD

```
User
 ├── Register/Login
 ├── Place Order
 ├── View Wallet

Backend
 ├── Auth Service
 ├── Order Service
 ├── Matching Engine
 ├── Wallet Service

Database
 ├── Users
 ├── Orders
 ├── Trades
 ├── Wallets
```

---

## 🧪 8. Matching Engine (Simplified Logic)

* Buy orders sorted by highest price
* Sell orders sorted by lowest price
* Match when:

  * Buy price ≥ Sell price
* Execute trade
* Update balances

---

## 🔐 9. Security Considerations (MVP)

* Password hashing (bcrypt)
* JWT authentication
* Input validation
* Rate limiting (optional)

---

## 🧰 10. Tech Stack

### Frontend

* React.js
* Axios
* Tailwind / CSS

### Backend

* Node.js
* Express.js
* JWT

### Database

* MongoDB

---

## ▶️ 11. How to Run the Project (Localhost)

### 📁 Folder Structure

```
mini-binance/
 ├── client/
 ├── server/
 ├── README.md
```

---

### 🔧 Backend Setup

```bash
cd server
npm install
npm start
```

Server runs at: `http://localhost:5000`

---

### 🎨 Frontend Setup

```bash
cd client
npm install
npm start
```

Frontend runs at: `http://localhost:3000`

---

## 🧪 12. Demo Credentials

```
Email: demo@user.com
Password: demo123
```

---

## 🚀 13. Future Enhancements

* Real-time order book (WebSockets)
* Candlestick charts
* Futures & margin trading
* Blockchain testnet integration
* Admin dashboard
* KYC upload flow

---

## 📚 14. Learning Outcomes

* Understand how Binance works internally
* Learn crypto exchange architecture
* Gain experience in fintech system design
* Hands-on backend + frontend integration

---

## 🧩 15. Hybrid Ramp Server (Demo)

This project also includes a **Hybrid Ramp demo backend** that simulates advanced Binance-like functionality such as **smart routing, liquidity aggregation, basket execution, and KYC tiers**. This backend is designed to visually and functionally support the frontend MVP.

---

### 📦 Purpose of the Hybrid Ramp Server

The Express-based demo server is used to:

* Provide **liquidity quotes and routing suggestions**
* Execute **basket-based crypto allocations**
* Index **simulated transactions**
* Simulate **KYC verification tiers**
* Optionally perform **on-chain settlement via a relayer**

> ⚠️ This server uses an **in-memory store** and is meant **only for demos and local development**.

---

### ⚡ Quick Start

```bash
cd server
npm install
npm start
```

---

### 🌱 Environment Variables (Optional)

These variables enable advanced or on-chain features:

* `RELAYER_PRIVATE_KEY` — Server-side private key for signing transactions
* `RPC_URL` — JSON-RPC endpoint (Infura / Alchemy)
* `ERC20_ABI` — Stringified ERC-20 ABI
* `ERC20_ADDRESS` — Optional default ERC-20 token
* `INSTITUTIONAL_THRESHOLD` — USD threshold for smart routing (default: 5000)

---

### 🔌 API Endpoints Overview

| Method | Endpoint              | Description                    |
| ------ | --------------------- | ------------------------------ |
| GET    | `/api/health`         | Health check                   |
| POST   | `/api/quote`          | Get liquidity sources          |
| POST   | `/api/route-order`    | Smart routing & execution plan |
| POST   | `/api/execute-basket` | Execute basket allocation      |
| GET    | `/api/txs`            | List recorded transactions     |
| POST   | `/api/kyc`            | Simulated KYC tier             |

---

### 🧠 Smart Routing Logic (Demo)

* Orders below threshold → retail routing
* Orders above threshold → institutional routing
* Optional on-chain execution using relayer

---

### 🔗 Relayer & On-Chain Settlement (Optional)

The server can act as a **transaction relayer**, submitting blockchain transactions on behalf of users.

To enable this feature:

1. Configure `.env` using `.env.example`
2. Set relayer and RPC credentials
3. Run the demo script:

```bash
node relayer-example.js
```

> 🔐 **Security Warning**: This relayer model is for **educational use only**. Never expose private keys in production. Use secure key vaults and signing services.

---

## 🏁 16. Conclusion

This **Mini Binance + Hybrid Ramp MVP** provides a realistic, end-to-end demonstration of how modern crypto platforms like Binance handle:

* Trading & order execution
* Smart liquidity routing
* Custodial wallet management
* KYC-based access control
* Optional on-chain settlement

It serves as a **strong foundation** for:

* FinTech hackathons
* Web3 system design practice
* Academic projects
* Startup MVP prototyping

---

💡 *Inspired by Binance, extended with Hybrid Ramp architecture, built for learning.*
