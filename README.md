# 🏧 Blockchain ATM Transaction Monitoring & Review Automation System

[![Node.js](https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=nodedotjs&logoColor=white)](https://nodejs.org/)
[![Express.js](https://img.shields.io/badge/Express.js-000000?style=for-the-badge&logo=express&logoColor=white)](https://expressjs.com/)
[![SQLite](https://img.shields.io/badge/SQLite-07405E?style=for-the-badge&logo=sqlite&logoColor=white)](https://sqlite.org/)
[![Socket.IO](https://img.shields.io/badge/Socket.io-010101?&style=for-the-badge&logo=Socket.io&logoColor=white)](https://socket.io/)

> **An enterprise-grade automation system I designed and directed to transform customer engagement for a 500+ Bitcoin ATM network, increasing review collection by 300% and driving significant business growth.**

## ⭐ My Role: Architect & Project Lead

As the architect for this solution, my role was to design the entire system, define its features, and direct its development using AI tools. I was responsible for:
- **Architecting the full-stack application**, including the Node.js backend, SQLite database schema, and real-time frontend.
- **Designing the core business logic** for multi-cryptocurrency transaction monitoring and automated customer engagement.
- **Directing the integration** of all third-party APIs (Blockchain explorers, Telegram, Zendesk).
- **Defining the requirements** for the analytics dashboard and all tracking metrics.

The following document describes the technical details and features of the system that was built based on my architecture and direction.

## 🚀 Business Impact

- **📈 300% increase** in customer review collection
- **🔄 80% reduction** in manual workflow processes
- **⚡ Real-time monitoring** of 500+ Bitcoin ATMs nationwide
- **💰 Direct revenue impact** through improved reputation and customer engagement

## 🏗️ System Architecture

```
┌─────────────────┐    ┌──────────────────┐    ┌─────────────────┐
│   Transaction   │───▶│   Blockchain     │───▶│   Review        │
│   Monitoring    │    │   Confirmation   │    │   Automation    │
└─────────────────┘    └──────────────────┘    └─────────────────┘
         │                       │                       │
         ▼                       ▼                       ▼
┌─────────────────┐    ┌──────────────────┐    ┌─────────────────┐
│   SQLite DB     │    │   Multi-Crypto   │    │   Telegram +    │
│   Analytics     │    │   API Support    │    │   Zendesk API   │
└─────────────────┘    └──────────────────┘    └─────────────────┘
```

## 🛠️ Technical Stack

### Backend & Database
- **Node.js** - Server-side runtime
- **Express.js** - Web application framework
- **SQLite3** - Lightweight database for analytics and tracking
- **Socket.IO** - Real-time bidirectional communication

### Blockchain Integration
- **Bitcoin (BTC)** - Mempool.space API
- **Ethereum (ETH)** - Etherscan API
- **USDC/USDT** - ERC-20 token tracking
- **Litecoin (LTC)** - Blockchair API

### Communication APIs
- **Telegram Bot API** - Automated notifications
- **Zendesk API** - Customer service integration
- **Dub.co / Bitly** - Link shortening and click tracking

### Frontend Dashboard
- **EJS Templates** - Server-side rendering
- **Socket.IO Client** - Real-time updates
- **Chart.js** - Data visualization
- **Bootstrap** - Responsive UI framework

## 🔥 Key Features

### 🔍 **Transaction Monitoring**
- Real-time tracking of Bitcoin ATM transactions
- Multi-cryptocurrency support (BTC, ETH, USDC, USDT, LTC)
- Automated blockchain confirmation verification
- Transaction status updates and notifications

### 📧 **Customer Engagement Automation**
- Intelligent review request timing based on transaction status
- Automated email campaigns via Zendesk integration
- Telegram notifications for immediate alerts
- Personalized customer outreach based on transaction data

### 📊 **Analytics & Tracking**
- Comprehensive review lifecycle tracking
- Click-through rate monitoring for review links
- Customer engagement metrics and reporting
- Historical data analysis and trends

### 🔗 **Link Management**
- Dynamic Google My Business review link generation
- Shortened URL creation with click tracking
- Anti-spam protection to prevent duplicate requests
- Conversion rate optimization through A/B testing

## 📋 Project Structure

```
atm-monitoring/
├── src/
│   ├── controllers/
│   │   ├── transactionController.js
│   │   ├── reviewController.js
│   │   └── analyticsController.js
│   ├── services/
│   │   ├── blockchainService.js
│   │   ├── telegramService.js
│   │   ├── zendeskService.js
│   │   └── linkService.js
│   ├── models/
│   │   ├── Transaction.js
│   │   ├── Review.js
│   │   └── Analytics.js
│   ├── routes/
│   │   ├── api.js
│   │   ├── dashboard.js
│   │   └── webhooks.js
│   └── utils/
│       ├── database.js
│       ├── logger.js
│       └── validators.js
├── public/
│   ├── css/
│   ├── js/
│   └── assets/
├── views/
│   ├── dashboard.ejs
│   ├── analytics.ejs
│   └── partials/
├── config/
│   ├── database.sql
│   ├── .env.example
│   └── config.js
├── tests/
│   ├── unit/
│   ├── integration/
│   └── e2e/
├── docs/
│   ├── API.md
│   ├── DEPLOYMENT.md
│   └── ARCHITECTURE.md
├── package.json
├── docker-compose.yml
└── README.md
```

## 🚀 Quick Start

### Prerequisites
- Node.js 18+ and npm
- SQLite3
- API keys for blockchain services
- Telegram Bot token
- Zendesk API credentials

### Installation

1. **Clone the repository**
```bash
git clone https://github.com/yourprofile/atm-monitoring.git
cd atm-monitoring
```

2. **Install dependencies**
```bash
npm install
```

3. **Configure environment variables**
```bash
cp config/.env.example .env
# Edit .env with your API keys and configuration
```

4. **Initialize database**
```bash
npm run db:init
```

5. **Start the application**
```bash
npm run dev  # Development mode
npm start    # Production mode
```

6. **Access the dashboard**
```
http://localhost:3000/dashboard
```

## 📊 API Documentation

### Transaction Endpoints
```javascript
GET    /api/transactions          // Get all transactions
POST   /api/transactions          // Create new transaction
GET    /api/transactions/:id      // Get specific transaction
PUT    /api/transactions/:id      // Update transaction status
```

### Review Endpoints
```javascript
GET    /api/reviews               // Get review requests
POST   /api/reviews/request       // Send review request
PUT    /api/reviews/:id/status    // Update review status
GET    /api/reviews/analytics     // Get review metrics
```

### Blockchain Endpoints
```javascript
GET    /api/blockchain/confirm/:txId    // Check confirmation status
GET    /api/blockchain/balance/:address // Get wallet balance
POST   /api/blockchain/webhook          // Blockchain webhook handler
```

## 🔧 Configuration

### Environment Variables
```env
# Database
DATABASE_PATH=./data/review_system.db

# Blockchain APIs
MEMPOOL_API_KEY=your_mempool_key
ETHERSCAN_API_KEY=your_etherscan_key
BLOCKCHAIR_API_KEY=your_blockchair_key

# Communication
TELEGRAM_BOT_TOKEN=your_telegram_token
ZENDESK_API_TOKEN=your_zendesk_token
ZENDESK_SUBDOMAIN=your_subdomain

# Link Shortening
DUB_API_KEY=your_dub_key
BITLY_ACCESS_TOKEN=your_bitly_token

# Application
PORT=3000
NODE_ENV=production
```

## 📈 Performance Metrics

- **Response Time**: < 200ms average API response
- **Uptime**: 99.9% system availability
- **Throughput**: 1000+ transactions processed per day
- **Scalability**: Handles 500+ concurrent ATM connections

## 🧪 Testing

```bash
npm test              # Run all tests
npm run test:unit     # Unit tests only
npm run test:integration  # Integration tests
npm run test:e2e      # End-to-end tests
npm run test:coverage # Coverage report
```

## 📦 Deployment

### Docker Deployment
```bash
docker-compose up -d
```

### Manual Deployment
```bash
npm run build
npm run deploy
```

## 🔒 Security Features

- **API Authentication** - JWT token-based security
- **Rate Limiting** - Prevents API abuse
- **Input Validation** - Comprehensive data sanitization
- **Secure Headers** - CORS and security headers configured
- **Environment Isolation** - Separate configs for dev/staging/prod

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙋‍♂️ Contact

**Tommy H** - Automation Engineer  
📧 Tommy.heredia24@gmail.com  
🔗 [LinkedIn](https://linkedin.com/in/theredia24)  

---

> **Note**: This system was built using AI-assisted development tools (Cursor, GitHub Copilot) combined with deep domain expertise in cryptocurrency operations and automation engineering.
