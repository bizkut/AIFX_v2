# AIFX v2 - AI-Powered Forex Trading Advisory System

<div align="center">

![Version](https://img.shields.io/badge/version-2.0.0-blue.svg)
![License](https://img.shields.io/badge/license-MIT-green.svg)
![Node](https://img.shields.io/badge/node-%3E%3D18.0.0-brightgreen.svg)
![Python](https://img.shields.io/badge/python-%3E%3D3.8-blue.svg)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-14+-blue.svg)
![TensorFlow](https://img.shields.io/badge/TensorFlow-2.10+-orange.svg)

**Intelligent Forex Trading Advisory System | 智能外匯交易顧問系統**

*Using machine learning and technical analysis to deliver real-time trading signals via Discord / LINE*

[Features](#-features) •
[System Architecture](#-system-architecture) •
[ML Training Process](#-machine-learning-training-architecture) •
[API Transmission](#-api-transmission-process) •
[FAQ](#-frequently-asked-questions)

</div>

---

## 📋 Table of Contents

- [Project Introduction](#-project-introduction)
- [Features](#-features)
- [System Architecture](#-system-architecture)
- [Technology Stack](#-technology-stack)
- [Directory Structure](#-directory-structure)
- [Quick Start](#-quick-start)
- [Environment Configuration](#-environment-configuration)
- [Machine Learning Training Architecture](#-machine-learning-training-architecture)
- [API Transmission Process](#-api-transmission-process)
- [User Identification System](#-user-identification-system)
- [Database Design](#-database-design)
- [Backtesting System](#-backtesting-system)
- [Notification System](#-notification-system)
- [Deployment Guide](#-deployment-guide)
- [Future Outlook](#-future-outlook)
- [Frequently Asked Questions](#-frequently-asked-questions)

---

## 📖 Project Introduction

### Background and Motivation

The foreign exchange market is the world's largest financial market, with a daily trading volume exceeding **$6.6 trillion**. However, for general investors, making correct trading decisions in this 24-hour market is extremely challenging.

**AIFX v2** aims to solve the following problems:

| Problem | Description |
|------|------|
| 🕐 **Time Constraints** | Investors cannot monitor the market 24/7 |
| 📊 **Information Overload** | Market data is complex and difficult to analyze quickly |
| 😰 **Emotional Interference** | Human trading is easily influenced by emotions |
| 📈 **Technical Barriers** | Technical analysis requires professional knowledge |

### Solution

AIFX v2 is an intelligent trading advisory system that integrates **artificial intelligence** with **technical analysis**, delivering real-time trading signals via **Discord** and **LINE**:

```
┌─────────────────────────────────────────────────────────────────────────┐
│                        AIFX v2 Core Value                                │
├─────────────────────────────────────────────────────────────────────────┤
│                                                                          │
│   🤖 Machine Learning Prediction      Uses LSTM deep learning models to analyze historical data │
│                                                                          │
│   📊 Multi-dimensional Analysis       Integrates technical indicators, market sentiment, price patterns │
│                                                                          │
│   🔔 Real-time Notifications          Delivers trading signals via Discord / LINE Bot │
│                                                                          │
│   📉 Backtesting Verification         Provides historical data backtesting to validate strategy effectiveness │
│                                                                          │
│   ⚠️ Risk Reminders                   Each signal includes risk warning prompts │
│                                                                          │
└─────────────────────────────────────────────────────────────────────────┘
```

### Project Goals

| Goal | Description | Status |
|------|------|----------|
| **Accuracy** | Improve signal accuracy through ML models | ✅ Achieved |
| **Real-time** | Millisecond-level signal delivery to Discord/LINE | ✅ Achieved |
| **Usability** | Interactive query via Bot commands | ✅ Achieved |
| **Reliability** | Microservices architecture ensures system stability | ✅ Achieved |
| **Scalability** | Modular design supports feature expansion | ✅ Achieved |

---

## ✨ Features

### System Feature Overview

```
┌─────────────────────────────────────────────────────────────────────────┐
│                       AIFX v2 Feature Architecture                       │
├─────────────────────────────────────────────────────────────────────────┤
│                                                                          │
│   ┌───────────────┐     ┌───────────────┐     ┌───────────────┐        │
│   │   Market Data │────▶│   AI Analysis │────▶│   Signal      │        │
│   │   Collection  │     │   Engine      │     │   Generation  │        │
│   │   Module      │     │               │     │   System      │        │
│   └───────────────┘     └───────────────┘     └───────┬───────┘        │
│          │                                             │                │
│          ▼                                             ▼                │
│   ┌───────────────┐                           ┌───────────────┐        │
│   │   Technical   │                           │   Bot         │        │
│   │   Indicators  │                           │   Notification│        │
│   │   Calculation │                           │   System      │        │
│   └───────────────┘                           └───────────────┘        │
│          │                                             │                │
│          ▼                                             ▼                │
│   ┌───────────────┐                         ┌─────────┬─────────┐     │
│   │   Backtesting │                         │ Discord │  LINE   │     │
│   │   Performance │                         │   Bot   │   Bot   │     │
│   │   Analysis    │                         └─────────┴─────────┘     │
│   └───────────────┘                                                     │
│                                                                          │
└─────────────────────────────────────────────────────────────────────────┘
```

### Core Feature Modules

#### 1. 📊 Market Data Module

| Feature | Description |
|------|------|
| **Multi-data Source Integration** | Alpha Vantage, Twelve Data, yFinance |
| **Real-time Quotes** | Real-time prices for major currency pairs |
| **Historical Data** | Supports multiple timeframes (15min/1h/1d/1w) |
| **Intelligent Caching** | Redis cache reduces API requests |

#### 2. 🤖 AI Prediction Engine

| Feature | Description |
|------|------|
| **LSTM Model** | Long Short-Term Memory network for price trend prediction |
| **Technical Indicators** | SMA, EMA, RSI, MACD, Bollinger Bands |
| **Sentiment Analysis** | NewsAPI news + Central bank policy sentiment (FinBERT/VADER) |
| **Signal Fusion** | Technical analysis + sentiment analysis weighted decision |
| **Confidence Score** | Each prediction includes confidence score (0-100%) |

**Sentiment Weight Mechanism** (Longer timeframes have greater sentiment influence):

| Timeframe | Technical Weight | Sentiment Weight | Description |
|----------|----------|----------|------|
| 15 minutes | 95% | 5% | Short-term focused on technicals |
| 1 hour | 85% | 15% | Balanced for swing trading |
| 4 hours | 70% | 30% | Medium-term considers sentiment |
| 1 day | 55% | 45% | Daily timeframe values fundamentals |
| 1 week | 40% | 60% | Long-term sentiment dominant |

#### 3. 📈 Trading Signal System

| Period Type | Timeframe | Suitable Traders |
|----------|----------|------------|
| **Intraday Trading** | 15 minutes | Short-term traders |
| **Swing Trading** | 1 hour | Swing traders |
| **Position Trading** | 1 day | Medium-term investors |
| **Long-term Trading** | 1 week | Long-term investors |

#### 4. 🔔 Bot Notification System

| Channel | Features |
|------|------|
| **Discord Bot** | Group push, personal subscriptions, slash command interaction |
| **LINE Bot** | Real-time push, interactive queries, subscription management |

#### 5. 📉 Backtesting System

| Feature | Description |
|------|------|
| **Historical Simulation** | Validate strategies using historical data |
| **Performance Metrics** | 8 key indicator analysis |
| **Visualization Reports** | Automatically generates 6 types of charts and HTML reports |

---

## 🏗 System Architecture

### Microservices Architecture Diagram

```
                              ┌─────────────────────────────────────────────┐
                              │               Client Layer                  │
                              ├─────────────────────────────────────────────┤
                              │                                              │
                              │         ┌─────────┐       ┌─────────┐      │
                              │         │ Discord │       │  LINE   │      │
                              │         │   App   │       │   App   │      │
                              │         └────┬────┘       └────┬────┘      │
                              │              │                  │           │
                              └──────────────┼──────────────────┼───────────┘
                                             │                  │
                    ┌────────────────────────┼──────────────────┼────────────────────────┐
                    │                        ▼                  ▼                        │
                    │              ┌─────────────┐      ┌─────────────┐                 │
                    │              │  Discord    │      │   LINE      │                 │
                    │              │  Bot        │      │   Bot       │                 │
                    │              └──────┬──────┘      └──────┬──────┘                 │
                    │                     │                    │                         │
                    │                     └─────────┬──────────┘                         │
                    │                               │ REST API                           │
                    │                               ▼                                    │
                    │  ┌────────────────────────────────────────────────────────────┐   │
                    │  │                    Backend API                              │   │
                    │  │                   (Port 3000)                               │   │
                    │  │  ┌──────────────────────────────────────────────────────┐  │   │
                    │  │  │  • User Management (Discord ID / LINE ID)            │  │   │
                    │  │  │  • Subscription Management                           │  │   │
                    │  │  │  • Trading Signal Generation & Storage               │  │   │
                    │  │  │  • Market Data Processing                            │  │   │
                    │  │  └──────────────────────────────────────────────────────┘  │   │
                    │  └────────────────────────┬───────────────────────────────────┘   │
                    │                           │                                        │
                    │           ┌───────────────┼───────────────┐                       │
                    │           ▼               ▼               ▼                       │
                    │  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐               │
                    │  │ PostgreSQL  │  │    Redis    │  │  ML Engine  │               │
                    │  │  Database   │  │    Cache    │  │ (Port 8000) │               │
                    │  └─────────────┘  └─────────────┘  └─────────────┘               │
                    │                                                                    │
                    │                    Service Layer                                  │
                    └────────────────────────────────────────────────────────────────────┘
```

### Service Communication Rules

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                          Service Communication Architecture                 │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                              │
│   Discord Bot ────── REST API ──────┐                                       │
│                                      │                                       │
│   LINE Bot ──────── REST API ───────┼────▶ Backend API (Port 3000)         │
│                                      │            │                          │
│                                      │            ├──── REST ────▶ ML Engine │
│                                      │            │               (Port 8000)│
│                                      │            │                          │
│                                      │            ▼                          │
│                                      │     ┌─────────────┐                  │
│                                      │     │ PostgreSQL  │                  │
│                                      │     │ + Redis     │                  │
│                                      │     └─────────────┘                  │
│                                                                              │
│   ╔═════════════════════════════════════════════════════════════════════╗   │
│   ║  Important Rules:                                                    ║   │
│   ║  • Only Backend can directly access PostgreSQL                       ║   │
│   ║  • Discord Bot / LINE Bot must go through Backend API                ║   │
│   ║  • ML Engine communicates with Backend via REST API                  ║   │
│   ║  • All inter-service communication uses REST API                     ║   │
│   ╚═════════════════════════════════════════════════════════════════════╝   │
│                                                                              │
└─────────────────────────────────────────────────────────────────────────────┘
```

---

## 🛠 Technology Stack

### Technology Stack Overview

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                           AIFX v2 Technology Stack                          │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                              │
│   ┌─────────────────────────────────────────────────────────────────────┐   │
│   │                        Backend Layer                                 │   │
│   │  Node.js 18 │ Express 4.18 │ Sequelize │ JWT │ API Key Auth         │   │
│   └─────────────────────────────────────────────────────────────────────┘   │
│                                      │                                       │
│                    ┌─────────────────┼─────────────────┐                    │
│                    ▼                 ▼                 ▼                    │
│   ┌─────────────────────┐ ┌─────────────────┐ ┌─────────────────────────┐  │
│   │   Data Layer        │ │   Cache Layer   │ │   ML Layer              │  │
│   │  PostgreSQL 14      │ │   Redis 6       │ │  Python 3.8             │  │
│   │  Sequelize ORM      │ │                 │ │  TensorFlow 2.10        │  │
│   └─────────────────────┘ └─────────────────┘ │  FastAPI                │  │
│                                               │  scikit-learn           │  │
│                                               └─────────────────────────┘  │
│                                                                              │
│   ┌─────────────────────────────────────────────────────────────────────┐   │
│   │                        Bot Layer                                     │   │
│   │  Discord.js 14 │ LINE Bot SDK 8 │ Axios                             │   │
│   └─────────────────────────────────────────────────────────────────────┘   │
│                                                                              │
└─────────────────────────────────────────────────────────────────────────────┘
```

### Detailed Technology List

#### Backend Technologies

| Technology | Version | Purpose |
|------|------|------|
| **Node.js** | ≥18.0.0 | JavaScript runtime environment |
| **Express.js** | ^4.18.0 | Web application framework |
| **Sequelize** | ^6.0.0 | ORM database operations |
| **PostgreSQL** | ≥14.0 | Relational database |
| **Redis** | ≥6.0 | Cache and Session |
| **Axios** | ^1.0.0 | HTTP request client |
| **Winston** | ^3.0.0 | Logging |
| **Joi** | ^17.0.0 | Request validation |

#### Machine Learning (ML Engine)

| Technology | Version | Purpose |
|------|------|------|
| **Python** | ≥3.8 | Programming language |
| **TensorFlow** | ≥2.10.0 | Deep learning framework |
| **Keras** | (built into TF) | High-level neural network API |
| **scikit-learn** | ≥1.0.0 | Machine learning tools |
| **Pandas** | ≥1.5.0 | Data processing |
| **NumPy** | ≥1.23.0 | Numerical computation |
| **FastAPI** | ≥0.100.0 | High-performance API framework |
| **Uvicorn** | ≥0.23.0 | ASGI server |
| **Matplotlib** | ≥3.7.0 | Chart plotting |
| **Seaborn** | ≥0.12.0 | Statistical visualization |

#### Bot Services

| Technology | Version | Purpose |
|------|------|------|
| **Discord.js** | ^14.0.0 | Discord Bot development |
| **LINE Bot SDK** | ^8.0.0 | LINE Bot development |
| **Axios** | ^1.0.0 | HTTP requests |

---

## 📁 Directory Structure

```
AIFX_v2/
│
├── 📂 backend/                      # Backend API Service
│   ├── 📂 src/
│   │   ├── 📂 config/              # Configuration files
│   │   │   ├── database.js         # Database configuration
│   │   │   └── redis.js            # Redis configuration
│   │   ├── 📂 controllers/         # Controllers
│   │   │   ├── signalController.js # Signal controller
│   │   │   └── discordController.js# Discord API controller
│   │   ├── 📂 middleware/          # Middleware
│   │   │   └── auth.js             # API Key authentication
│   │   ├── 📂 models/              # Sequelize models
│   │   │   ├── UserDiscordSettings.js  # Discord users
│   │   │   ├── UserLineSettings.js     # LINE users
│   │   │   ├── TradingSignal.js        # Trading signals
│   │   │   └── MarketData.js           # Market data
│   │   ├── 📂 routes/              # Route definitions
│   │   │   └── 📂 api/v1/          # API v1 routes
│   │   ├── 📂 services/            # Business logic services
│   │   │   ├── forexService.js     # Forex data service
│   │   │   └── signalService.js    # Signal service
│   │   └── app.js                  # Application entry point
│   ├── package.json
│   └── .env.example
│
├── 📂 ml_engine/                    # Machine Learning Engine ⭐
│   ├── 📂 api/                     # ML API Service
│   │   ├── ml_server.py            # FastAPI server
│   │   └── prediction_service.py   # Prediction service
│   ├── 📂 models/                  # Trained models
│   │   └── lstm_model.h5           # LSTM model weights
│   ├── 📂 training/                # Model training
│   │   ├── train_lstm.py           # LSTM training script
│   │   └── feature_engineering.py  # Feature engineering
│   ├── 📂 data_processing/         # Data processing
│   │   ├── yfinance_fetcher.py     # yFinance data fetcher
│   │   └── data_preprocessor.py    # Data preprocessor
│   ├── 📂 backtest/                # Backtesting system
│   │   ├── backtest_engine.py      # Backtest engine
│   │   ├── historical_backtest.py  # Historical backtest
│   │   ├── chart_generator.py      # Chart generator
│   │   └── 📂 reports/             # Backtest reports
│   ├── 📂 scripts/                 # Execution scripts
│   │   ├── daily_incremental_training.py   # Daily incremental training
│   │   └── weekly_full_training.py         # Weekly full training
│   ├── requirements.txt
│   └── start.sh
│
├── 📂 discord_bot/                  # Discord Bot Service
│   ├── bot.js                      # Bot entry point
│   ├── deploy-commands.js          # Slash command deployment
│   ├── 📂 commands/                # Bot commands
│   ├── 📂 events/                  # Event handlers
│   └── 📂 services/                # Bot services
│
├── 📂 line_bot/                     # LINE Bot Service
│   ├── bot.js                      # Bot entry point
│   ├── 📂 handlers/                # Message handlers
│   └── 📂 services/                # Bot services
│       ├── backendClient.js        # Backend API client
│       └── messageBuilder.js       # Message builder
│
├── 📂 database/                     # Database related
│   ├── 📂 migrations/              # Database migrations
│   └── 📂 seeders/                 # Seed data
│
├── 📄 CLAUDE.md                     # Claude Code standards
├── 📄 README.md                     # Project documentation (This file)
└── 📄 .gitignore                    # Git ignore rules
```

---

## 🚀 Quick Start

### Prerequisites

| Software | Version | Necessity |
|------|------|--------|
| Node.js | ≥ 18.0.0 | Required |
| Python | ≥ 3.8 | Required |
| PostgreSQL | ≥ 14.0 | Required |
| Redis | ≥ 6.0 | Required |
| Git | Latest | Required |

### Installation Steps

#### Step 1: Clone Project

```bash
git clone https://github.com/LazOof69/AIFX_v2.git
cd AIFX_v2
```

#### Step 2: Install Backend Dependencies

```bash
cd backend
npm install
cp .env.example .env
# Edit .env to configure database and API keys
```

#### Step 3: Install ML Engine Dependencies

```bash
cd ../ml_engine
pip install -r requirements.txt
```

#### Step 4: Install Bot Dependencies

```bash
# Discord Bot
cd ../discord_bot
npm install

# LINE Bot
cd ../line_bot
npm install
```

#### Step 5: Setup Database

```bash
# Create database
createdb aifx_v2_dev

# Run migrations
cd ../backend
npx sequelize-cli db:migrate
```

#### Step 6: Start Services

```bash
# Terminal 1 - Backend API
cd backend && npm run dev

# Terminal 2 - ML Engine
cd ml_engine && python api/ml_server.py

# Terminal 3 - Discord Bot
cd discord_bot && node bot.js

# Terminal 4 - LINE Bot
cd line_bot && node bot.js
```

#### Step 7: Verify Services

| Service | URL | Description |
|------|-----|------|
| Backend API | http://localhost:3000 | API Service |
| ML Engine | http://localhost:8000 | ML Prediction Service |

---

## ⚙ Environment Configuration

### Backend (.env)

```env
# ===== Service Config =====
NODE_ENV=development
PORT=3000

# ===== Database =====
DATABASE_URL=postgresql://user:password@localhost:5432/aifx_v2_dev

# ===== Redis =====
REDIS_URL=redis://localhost:6379

# ===== External API Keys =====
ALPHA_VANTAGE_KEY=your-alpha-vantage-api-key
TWELVE_DATA_KEY=your-twelve-data-api-key

# ===== ML Engine =====
ML_API_URL=http://localhost:8000

# ===== Discord Bot =====
DISCORD_BOT_TOKEN=your-discord-bot-token
DISCORD_CLIENT_ID=your-discord-client-id

# ===== LINE Bot =====
LINE_CHANNEL_ACCESS_TOKEN=your-line-channel-access-token
LINE_CHANNEL_SECRET=your-line-channel-secret

# ===== Inter-service API Keys (64-char hex) =====
API_KEY=your-64-character-hex-api-key-for-discord
LINE_BOT_API_KEY=your-64-character-hex-api-key-for-line
```

---

## 🧠 Machine Learning Training Architecture

### Complete Training Flow

```
┌──────────────────────────────────────────────────────────────────────────────┐
│                        LSTM Model Training Complete Flow                      │
├──────────────────────────────────────────────────────────────────────────────┤
│                                                                               │
│  ╔═══════════════════════════════════════════════════════════════════════╗   │
│  ║                     Step 1: Data Collection                            ║   │
│  ╚═══════════════════════════════════════════════════════════════════════╝   │
│                                                                               │
│      ┌─────────────┐    ┌─────────────┐    ┌─────────────┐                  │
│      │ yFinance    │    │Alpha Vantage│    │ Twelve Data │                  │
│      │ (Primary)   │    │ (Backup)    │    │ (Backup)    │                  │
│      └──────┬──────┘    └──────┬──────┘    └──────┬──────┘                  │
│             │                  │                  │                          │
│             └──────────────────┼──────────────────┘                          │
│                                ▼                                             │
│                    ┌───────────────────────┐                                 │
│                    │   Raw OHLCV Data      │                                 │
│                    │   (Open, High, Low,   │                                 │
│                    │    Close, Volume)     │                                 │
│                    └───────────┬───────────┘                                 │
│                                │                                             │
│  ╔═══════════════════════════════════════════════════════════════════════╗   │
│  ║                     Step 2: Feature Engineering                        ║   │
│  ╚═══════════════════════════════════════════════════════════════════════╝   │
│                                │                                             │
│                                ▼                                             │
│    ┌─────────────────────────────────────────────────────────────────────┐   │
│    │                      Technical Indicator Calculation                 │   │
│    │  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐                 │   │
│    │  │ Moving Avg  │  │ Momentum    │  │ Volatility  │                 │   │
│    │  │ • SMA(5)    │  │ • RSI(14)   │  │ • BB Upper  │                 │   │
│    │  │ • SMA(20)   │  │ • MACD      │  │ • BB Lower  │                 │   │
│    │  │ • EMA(12)   │  │ • MACD Sig  │  │             │                 │   │
│    │  │ • EMA(26)   │  │             │  │             │                 │   │
│    │  └─────────────┘  └─────────────┘  └─────────────┘                 │   │
│    └─────────────────────────────────────────────────────────────────────┘   │
│                                │                                             │
│                                ▼                                             │
│                    ┌───────────────────────┐                                 │
│                    │   Feature Vector(12)  │                                 │
│                    │   [O,H,L,C,V,SMA5,    │                                 │
│                    │    SMA20,EMA12,RSI,   │                                 │
│                    │    MACD,BB_U,BB_L]    │                                 │
│                    └───────────┬───────────┘                                 │
│                                │                                             │
│  ╔═══════════════════════════════════════════════════════════════════════╗   │
│  ║                     Step 3: Preprocessing                              ║   │
│  ╚═══════════════════════════════════════════════════════════════════════╝   │
│                                │                                             │
│                                ▼                                             │
│    ┌─────────────────────────────────────────────────────────────────────┐   │
│    │                      Preprocessing Steps                             │   │
│    │                                                                      │   │
│    │  1. Standardization (StandardScaler)                                │   │
│    │     └── Scale data to mean=0, std=1                                 │   │
│    │                                                                      │   │
│    │  2. Sequencing (Windowing)                                          │   │
│    │     └── Convert data to sequences of 60 time steps                  │   │
│    │     └── Input: [t-59, t-58, ..., t-1, t]                            │   │
│    │     └── Output: t+1 Direction (Long/Short/Standby)                  │   │
│    │                                                                      │   │
│    │  3. Labeling                                                        │   │
│    │     └── Generate 3 classes of labels based on future price change   │   │
│    │     └── Up > 0.1% → Long (Buy)                                      │   │
│    │     └── Down > 0.1% → Short (Sell)                                  │   │
│    │     └── Others → Standby (Hold)                                     │   │
│    │                                                                      │   │
│    │  4. Data Splitting                                                  │   │
│    │     └── Training Set: 80%                                           │   │
│    │     └── Test Set: 20%                                               │   │
│    └─────────────────────────────────────────────────────────────────────┘   │
│                                │                                             │
│  ╔═══════════════════════════════════════════════════════════════════════╗   │
│  ║                     Step 4: Model Training                             ║   │
│  ╚═══════════════════════════════════════════════════════════════════════╝   │
│                                │                                             │
│                                ▼                                             │
│    ┌─────────────────────────────────────────────────────────────────────┐   │
│    │                      LSTM Neural Network Architecture                │   │
│    │                                                                      │   │
│    │  Input: (batch_size, 60, 12)                                        │   │
│    │     │                                                                │   │
│    │     ▼                                                                │   │
│    │  ┌────────────────────────────────────┐                             │   │
│    │  │  LSTM Layer 1 (128 units)          │                             │   │
│    │  │  return_sequences=True             │                             │   │
│    │  └──────────────────┬─────────────────┘                             │   │
│    │                     ▼                                                │   │
│    │  ┌────────────────────────────────────┐                             │   │
│    │  │  LSTM Layer 2 (64 units)           │                             │   │
│    │  │  return_sequences=False            │                             │   │
│    │  └──────────────────┬─────────────────┘                             │   │
│    │                     ▼                                                │   │
│    │  ┌────────────────────────────────────┐                             │   │
│    │  │  Dropout (0.2)                     │  ← Prevent Overfitting      │   │
│    │  └──────────────────┬─────────────────┘                             │   │
│    │                     ▼                                                │   │
│    │  ┌────────────────────────────────────┐                             │   │
│    │  │  Dense (32 units, ReLU)            │                             │   │
│    │  └──────────────────┬─────────────────┘                             │   │
│    │                     ▼                                                │   │
│    │  ┌────────────────────────────────────┐                             │   │
│    │  │  Dense (3 units, Softmax)          │  ← Output 3 class probs     │   │
│    │  └──────────────────┬─────────────────┘                             │   │
│    │                     ▼                                                │   │
│    │  Output: [P(Long), P(Short), P(Standby)]                            │   │
│    │                                                                      │   │
│    │  Training Parameters:                                               │   │
│    │  • Optimizer: Adam (learning_rate=0.001)                            │   │
│    │  • Loss Function: Categorical Crossentropy                          │   │
│    │  • Batch Size: 32                                                   │   │
│    │  • Epochs: 100 epochs                                               │   │
│    │  • Early Stopping: patience=10 (Prevent Overfitting)                │   │
│    └─────────────────────────────────────────────────────────────────────┘   │
│                                │                                             │
│  ╔═══════════════════════════════════════════════════════════════════════╗   │
│  ║                     Step 5: Model Saving                               ║   │
│  ╚═══════════════════════════════════════════════════════════════════════╝   │
│                                │                                             │
│                                ▼                                             │
│                    ┌───────────────────────┐                                 │
│                    │  Saved Files:         │                                 │
│                    │  • lstm_model.h5      │  ← Model Weights               │
│                    │  • scaler.pkl         │  ← Scaler                      │
│                    │  • config.json        │  ← Model Config                │
│                    └───────────────────────┘                                 │
│                                                                               │
└──────────────────────────────────────────────────────────────────────────────┘
```

### Training Schedule

| Training Type | Frequency | Script | Description |
|----------|------|------|------|
| **Full Training** | Weekly | `weekly_full_training.py` | Retrain using all historical data |
| **Incremental Training** | Daily | `daily_incremental_training.py` | Fine-tune using latest data |

### Execute Training

```bash
# Enter ML Engine directory
cd ml_engine

# Full Training (approx. 30-60 mins)
python scripts/weekly_full_training.py

# Incremental Training (approx. 5-10 mins)
python scripts/daily_incremental_training.py
```

---

## 📡 API Transmission Process

### Complete API Call Flow

```
┌──────────────────────────────────────────────────────────────────────────────┐
│                        API Transmission Complete Flow                         │
├──────────────────────────────────────────────────────────────────────────────┤
│                                                                               │
│  ╔═══════════════════════════════════════════════════════════════════════╗   │
│  ║           Scenario 1: Discord Bot Gets Trading Signal                  ║   │
│  ╚═══════════════════════════════════════════════════════════════════════╝   │
│                                                                               │
│   Discord User                Discord Bot              Backend API            │
│       │                          │                        │                   │
│       │   /signal EUR/USD        │                        │                   │
│       │─────────────────────────▶│                        │                   │
│       │                          │                        │                   │
│       │                          │  GET /api/v1/discord/signals/EUR/USD      │
│       │                          │  Headers:                                  │
│       │                          │    X-API-Key: <64-char API Key>           │
│       │                          │────────────────────────▶│                  │
│       │                          │                        │                   │
│       │                          │                        │ ┌──────────────┐ │
│       │                          │                        │ │ Verify Key   │ │
│       │                          │                        │ └──────┬───────┘ │
│       │                          │                        │        │         │
│       │                          │                        │        ▼         │
│       │                          │                        │ ┌──────────────┐ │
│       │                          │                        │ │Check Redis   │ │
│       │                          │                        │ │Cache         │ │
│       │                          │                        │ └──────┬───────┘ │
│       │                          │                        │        │         │
│       │                          │                        │   Hit?  │ Miss   │
│       │                          │                        │    ▼    │   │    │
│       │                          │                        │ Return  │   │    │
│       │                          │                        │ Cache   │   ▼    │
│       │                          │                        │        │ ┌──────┐│
│       │                          │                        │        │ │Call  ││
│       │                          │                        │        │ │ML API││
│       │                          │                        │        │ └──┬───┘│
│       │                          │                        │        │    │    │
│       │                          │  Response:            │◀───────┴────┘    │
│       │                          │  {                     │                   │
│       │                          │    "success": true,    │                   │
│       │                          │    "data": {           │                   │
│       │                          │      "pair": "EUR/USD",│                   │
│       │                          │      "action": "long", │                   │
│       │                          │      "confidence": 75, │                   │
│       │                          │      "entry_price": 1.0850,               │
│       │                          │      "stop_loss": 1.0820,                 │
│       │                          │      "take_profit": 1.0920                │
│       │                          │    }                   │                   │
│       │                          │  }                     │                   │
│       │                          │◀───────────────────────│                   │
│       │                          │                        │                   │
│       │  📊 Signal Embed Message │                        │                   │
│       │◀─────────────────────────│                        │                   │
│       │                          │                        │                   │
│                                                                               │
│  ╔═══════════════════════════════════════════════════════════════════════╗   │
│  ║           Scenario 2: LINE Bot Gets Trading Signal                     ║   │
│  ╚═══════════════════════════════════════════════════════════════════════╝   │
│                                                                               │
│   LINE User                   LINE Bot                 Backend API            │
│       │                          │                        │                   │
│       │   "Signal"               │                        │                   │
│       │─────────────────────────▶│                        │                   │
│       │                          │                        │                   │
│       │                          │  GET /api/v1/line/signals                 │
│       │                          │  Headers:                                  │
│       │                          │    Authorization: Bearer <API_KEY>        │
│       │                          │────────────────────────▶│                  │
│       │                          │                        │                   │
│       │                          │                        │ (Same flow)      │
│       │                          │                        │                   │
│       │                          │  Response: { signals } │                   │
│       │                          │◀───────────────────────│                   │
│       │                          │                        │                   │
│       │   Flex Message          │                        │                   │
│       │◀─────────────────────────│                        │                   │
│       │                          │                        │                   │
│                                                                               │
│  ╔═══════════════════════════════════════════════════════════════════════╗   │
│  ║           Scenario 3: Backend Calls ML Engine for Prediction           ║   │
│  ╚═══════════════════════════════════════════════════════════════════════╝   │
│                                                                               │
│   Backend API                                          ML Engine              │
│       │                                                   │                   │
│       │  POST /api/v1/predict                             │                   │
│       │  Body: {                                          │                   │
│       │    "pair": "EUR/USD",                             │                   │
│       │    "timeframe": "1h",                             │                   │
│       │    "data": [ ... OHLCV array ... ]                │                   │
│       │  }                                                │                   │
│       │──────────────────────────────────────────────────▶│                   │
│       │                                                   │                   │
│       │                                                   │ ┌──────────────┐ │
│       │                                                   │ │ 1. Preprocess│ │
│       │                                                   │ │    Standardize│ │
│       │                                                   │ └──────┬───────┘ │
│       │                                                   │        ▼         │
│       │                                                   │ ┌──────────────┐ │
│       │                                                   │ │ 2. Feat Eng  │ │
│       │                                                   │ │    Indicators│ │
│       │                                                   │ └──────┬───────┘ │
│       │                                                   │        ▼         │
│       │                                                   │ ┌──────────────┐ │
│       │                                                   │ │ 3. LSTM Infer│ │
│       │                                                   │ │    Prediction│ │
│       │                                                   │ └──────┬───────┘ │
│       │                                                   │        ▼         │
│       │  Response:                                        │                   │
│       │  {                                                │                   │
│       │    "prediction": "long",                          │                   │
│       │    "confidence": 0.75,                            │                   │
│       │    "probabilities": {                             │                   │
│       │      "long": 0.75,                                │                   │
│       │      "short": 0.15,                               │                   │
│       │      "standby": 0.10                              │                   │
│       │    },                                             │                   │
│       │    "factors": {                                   │                   │
│       │      "technical": 0.80,                           │                   │
│       │      "trend": 0.72                                │                   │
│       │    }                                              │                   │
│       │  }                                                │                   │
│       │◀──────────────────────────────────────────────────│                   │
│       │                                                   │                   │
│                                                                               │
└──────────────────────────────────────────────────────────────────────────────┘
```

### API Authentication

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                        API Authentication Flow                               │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                              │
│   ┌─────────────────────────────────────────────────────────────────────┐   │
│   │                     Method 1: X-API-Key Header                       │   │
│   │                        (Used by Discord Bot)                         │   │
│   └─────────────────────────────────────────────────────────────────────┘   │
│                                                                              │
│   Request:                                                                   │
│   GET /api/v1/discord/signals/EUR/USD                                       │
│   Headers:                                                                   │
│     X-API-Key: 64-char hex key                                              │
│                                                                              │
│   Verification:                                                              │
│   1. Check if X-API-Key header exists                                       │
│   2. Compare with environment variable API_KEY                              │
│   3. Success → Continue processing                                          │
│   4. Failure → Return 401 Unauthorized                                      │
│                                                                              │
│   ┌─────────────────────────────────────────────────────────────────────┐   │
│   │                     Method 2: Bearer Token                           │   │
│   │                        (Used by LINE Bot)                            │   │
│   └─────────────────────────────────────────────────────────────────────┘   │
│                                                                              │
│   Request:                                                                   │
│   GET /api/v1/line/signals                                                  │
│   Headers:                                                                   │
│     Authorization: Bearer 64-char hex key                                   │
│                                                                              │
│   Verification:                                                              │
│   1. Check if Authorization header exists                                   │
│   2. Extract token after Bearer                                             │
│   3. Check if token length is 64 chars (Distinguish from JWT)               │
│   4. Compare with environment variable LINE_BOT_API_KEY                     │
│   5. Success → Continue processing                                          │
│   6. Failure → Return 401 Unauthorized                                      │
│                                                                              │
│   ┌─────────────────────────────────────────────────────────────────────┐   │
│   │                     API Key vs JWT Distinction                       │   │
│   └─────────────────────────────────────────────────────────────────────┘   │
│                                                                              │
│   Logic:                                                                     │
│   • API Key: 64 chars hex, no "."                                           │
│   • JWT Token: Longer, contains "." (header.payload.signature)              │
│                                                                              │
│   Code:                                                                      │
│   if (token.length === 64 && !token.includes('.')) {                        │
│     // Is API Key                                                           │
│   } else {                                                                   │
│     // Is JWT Token                                                         │
│   }                                                                          │
│                                                                              │
└─────────────────────────────────────────────────────────────────────────────┘
```

### API Endpoints

| Endpoint | Method | Description | Auth |
|------|------|------|------|
| `/api/v1/discord/signals` | GET | Get all trading signals | API Key |
| `/api/v1/discord/signals/:pair` | GET | Get signal for specific pair | API Key |
| `/api/v1/discord/users/:discordId` | GET | Get user subscription status | API Key |
| `/api/v1/discord/users/:discordId/subscribe` | POST | User subscribe | API Key |
| `/api/v1/line/signals` | GET | Get all trading signals | Bearer Token |
| `/api/v1/line/signals/:pair` | GET | Get signal for specific pair | Bearer Token |
| `/api/v1/line/users/:lineId` | GET | Get user subscription status | Bearer Token |
| `/health` | GET | Health check | None |

### Response Format

```json
// Success Response
{
  "success": true,
  "data": {
    "pair": "EUR/USD",
    "action": "long",
    "confidence": 75,
    "entry_price": 1.0850,
    "stop_loss": 1.0820,
    "take_profit": 1.0920,
    "period": "swing",
    "timeframe": "1h",
    "created_at": "2025-11-29T10:30:00Z"
  },
  "error": null,
  "metadata": {
    "timestamp": "2025-11-29T10:30:00Z",
    "version": "v1"
  }
}

// Error Response
{
  "success": false,
  "data": null,
  "error": {
    "code": "UNAUTHORIZED",
    "message": "Invalid API key"
  },
  "metadata": {
    "timestamp": "2025-11-29T10:30:00Z",
    "version": "v1"
  }
}
```

---

## 👤 User Identification System

### User Identification Method

**This system does not use traditional Email/password registration**. Instead, it uses unique identifiers from Bot platforms to identify users:

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                        User Identification Architecture                      │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                              │
│   ┌─────────────────────────────────────────────────────────────────────┐   │
│   │                     Discord User Identification                      │   │
│   └─────────────────────────────────────────────────────────────────────┘   │
│                                                                              │
│   • ID: Discord User ID (Snowflake ID)                                      │
│   • Format: 18-19 digits (e.g., 123456789012345678)                         │
│   • Retrieval: Discord.js interaction.user.id                               │
│   • Storage Table: user_discord_settings                                    │
│                                                                              │
│   ┌─────────────────────────────────────────────────────────────────────┐   │
│   │                     LINE User Identification                         │   │
│   └─────────────────────────────────────────────────────────────────────┘   │
│                                                                              │
│   • ID: LINE User ID                                                        │
│   • Format: U + 32 hex chars (e.g., U1234567890abcdef1234567890abcdef)      │
│   • Retrieval: LINE Bot SDK event.source.userId                             │
│   • Storage Table: user_line_settings                                       │
│                                                                              │
│   ┌─────────────────────────────────────────────────────────────────────┐   │
│   │                     User First Interaction Flow                      │   │
│   └─────────────────────────────────────────────────────────────────────┘   │
│                                                                              │
│   Discord:                                                                   │
│   1. User types /subscribe in Discord                                       │
│   2. Bot gets interaction.user.id                                           │
│   3. Bot calls POST /api/v1/discord/users/{discordId}/subscribe             │
│   4. Backend creates record in user_discord_settings                        │
│   5. User starts receiving signals                                          │
│                                                                              │
│   LINE:                                                                      │
│   1. User sends "Subscribe" (訂閱) in LINE                                  │
│   2. Bot gets event.source.userId                                           │
│   3. Bot calls POST /api/v1/line/users/{lineId}/subscribe                   │
│   4. Backend creates record in user_line_settings                           │
│   5. User starts receiving signals                                          │
│                                                                              │
└─────────────────────────────────────────────────────────────────────────────┘
```

### User Table Structure

```sql
-- Discord User Table
CREATE TABLE user_discord_settings (
    id SERIAL PRIMARY KEY,
    discord_id VARCHAR(20) UNIQUE NOT NULL,  -- Discord User ID
    guild_id VARCHAR(20),                     -- Guild ID (Optional)
    is_subscribed BOOLEAN DEFAULT false,      -- Subscription Status
    preferred_pairs TEXT[],                   -- Preferred Pairs
    notification_enabled BOOLEAN DEFAULT true,
    created_at TIMESTAMP DEFAULT NOW(),
    updated_at TIMESTAMP DEFAULT NOW()
);

-- LINE User Table
CREATE TABLE user_line_settings (
    id SERIAL PRIMARY KEY,
    line_user_id VARCHAR(50) UNIQUE NOT NULL, -- LINE User ID
    display_name VARCHAR(100),                 -- Display Name (Optional)
    is_subscribed BOOLEAN DEFAULT false,       -- Subscription Status
    preferred_pairs TEXT[],                    -- Preferred Pairs
    notification_enabled BOOLEAN DEFAULT true,
    created_at TIMESTAMP DEFAULT NOW(),
    updated_at TIMESTAMP DEFAULT NOW()
);
```

---

## 🗄 Database Design

### ER Diagram

```
┌─────────────────────┐                   ┌─────────────────────┐
│user_discord_settings│                   │  user_line_settings │
├─────────────────────┤                   ├─────────────────────┤
│ id (PK)             │                   │ id (PK)             │
│ discord_id (UNIQUE) │                   │ line_user_id(UNIQUE)│
│ guild_id            │                   │ display_name        │
│ is_subscribed       │                   │ is_subscribed       │
│ preferred_pairs     │                   │ preferred_pairs     │
│ notification_enabled│                   │ notification_enabled│
│ created_at          │                   │ created_at          │
│ updated_at          │                   │ updated_at          │
└─────────────────────┘                   └─────────────────────┘

┌─────────────────┐       ┌─────────────────┐       ┌─────────────────┐
│ trading_signals │       │   market_data   │       │backtest_results │
├─────────────────┤       ├─────────────────┤       ├─────────────────┤
│ id (PK)         │       │ id (PK)         │       │ id (PK)         │
│ pair            │       │ pair            │       │ pair            │
│ action          │       │ timeframe       │       │ period          │
│ confidence      │       │ open            │       │ timeframe       │
│ entry_price     │       │ high            │       │ total_trades    │
│ stop_loss       │       │ low             │       │ win_rate        │
│ take_profit     │       │ close           │       │ profit_factor   │
│ period          │       │ volume          │       │ max_drawdown    │
│ timeframe       │       │ timestamp       │       │ sharpe_ratio    │
│ created_at      │       │ created_at      │       │ net_profit      │
└─────────────────┘       └─────────────────┘       │ created_at      │
                                                     └─────────────────┘
```

### Table Description

| Table | Description |
|--------|------|
| `user_discord_settings` | Discord user settings and subscription status |
| `user_line_settings` | LINE user settings and subscription status |
| `trading_signals` | Trading signal records |
| `market_data` | Historical market data |
| `backtest_results` | Backtest result summary |
| `backtest_trades` | Backtest trade details |

---

## 📊 Backtesting System

### Performance Metrics (8 Items)

| Metric | Description | Calculation |
|------|------|----------|
| **Win Rate** | Win Rate | Winning Trades ÷ Total Trades × 100% |
| **Profit Factor** | Profit Factor | Gross Profit ÷ Gross Loss |
| **Total Trades** | Total Trades | Number of completed trades |
| **Net Profit** | Net Profit | Gross Profit - Gross Loss |
| **Avg Win** | Avg Win | Average profit per winning trade |
| **Avg Loss** | Avg Loss | Average loss per losing trade |
| **Max Drawdown** | Max Drawdown | Maximum decline in equity curve |
| **Sharpe Ratio** | Sharpe Ratio | (Return - Risk-free Rate) ÷ Std Dev |

### Execute Backtest

```bash
cd ml_engine
python backtest/run_historical_backtest.py
```

### Backtest Results Example

| Pair | Period | Trades | Win Rate | Profit Factor | Net Profit |
|--------|------|--------|------|--------|--------|
| EUR/USD | Intraday | 9 | 33.3% | 1.85 | $227 |
| EUR/USD | Swing | 25 | 36.0% | 0.57 | -$886 |
| **USD/JPY** | **Swing** | **29** | **51.7%** | **1.73** | **$2,103** |
| GBP/USD | Position | 4 | 50.0% | 1.43 | $540 |

---

## 🔔 Notification System

### Discord Bot Commands

| Command | Description |
|------|------|
| `/signal` | Query latest trading signal |
| `/signal [pair]` | Query signal for specific pair |
| `/subscribe` | Subscribe to signal notifications |
| `/unsubscribe` | Cancel subscription |
| `/status` | View subscription status |
| `/help` | Show help message |

### LINE Bot Commands

| Command | Description |
|------|------|
| `訂閱` (Subscribe) | Subscribe to trading signals |
| `取消訂閱` (Unsubscribe) | Cancel subscription |
| `訊號` (Signal) | Query all latest signals |
| `EUR/USD` | Query signal for specific pair |
| `狀態` (Status) | View subscription status |
| `幫助` (Help) | Show help message |

### Signal Push Format

```
📊 AIFX Trading Signal

Pair: EUR/USD
Action: Long (Buy)
Confidence: 75%
Period: Swing (1H)
Time: 2025-11-29 10:30:00

⚠️ This system provides directional suggestions only. Decide entry price and risk management at your own discretion.
```

---

## 🌐 Deployment Guide

### PM2 Deployment

```bash
# Install PM2
npm install -g pm2

# Start Backend
cd backend && pm2 start npm --name "aifx-backend" -- run dev

# Start ML Engine
cd ../ml_engine && pm2 start python --name "aifx-ml" -- api/ml_server.py

# Start Discord Bot
cd ../discord_bot && pm2 start npm --name "aifx-discord" -- start

# Start LINE Bot
cd ../line_bot && pm2 start npm --name "aifx-line" -- start

# Check Status
pm2 status

# Save Configuration
pm2 save
pm2 startup
```

### Service Ports

| Service | Port | Description |
|------|------|------|
| Backend API | 3000 | REST API Service |
| ML Engine | 8000 | Machine Learning Prediction Service |
| PostgreSQL | 5432 | Database |
| Redis | 6379 | Cache Service |

---

## 🔮 Future Outlook

- Improve ML model prediction accuracy
- Support more currency pairs and markets

---

## ❓ Frequently Asked Questions

### Q1: How accurate is the system's prediction?

According to backtest results, the best performing combination (USD/JPY Swing) achieved a win rate of **51.7%**. We continuously optimize models to improve accuracy.

### Q2: Which currency pairs are supported?

Currently supports three major currency pairs:
- EUR/USD (Euro/US Dollar)
- USD/JPY (US Dollar/Japanese Yen)
- GBP/USD (British Pound/US Dollar)

### Q3: How often are signals updated?

| Period | Update Frequency |
|------|----------|
| Intraday Trading | Every 15 minutes |
| Swing Trading | Every 1 hour |
| Position Trading | Every 1 day |
| Long-term Trading | Every 1 week |

### Q4: How do users subscribe to signals?

Users just need to type `/subscribe` in Discord or send "Subscribe" (訂閱) in LINE. The system will automatically record the user's platform ID and start pushing signals. **No separate account registration required.**

---

## ⚠️ Disclaimer

**Important Reminder**:

1. Trading signals provided by this system are for reference only and do not constitute investment advice.
2. Forex trading involves high risks and may lead to financial loss.
3. Past backtest performance does not guarantee future results.
4. Users should assess risks and make trading decisions at their own discretion.
5. The development team is not responsible for any trading losses.

---

## 📄 License

This project is licensed under the MIT License.

---

## 🙏 Acknowledgements

- [Alpha Vantage](https://www.alphavantage.co/) - Forex Data API
- [Twelve Data](https://twelvedata.com/) - Market Data API
- [yFinance](https://github.com/ranaroussi/yfinance) - Historical Data
- [TensorFlow](https://www.tensorflow.org/) - Deep Learning Framework
- Open Source Community

---

---

## 📝 Changelog

### 2025-12-02

#### Fixes
- **Discord Bot API Key Auth**: Fixed `authenticateFlexible` middleware to support `DISCORD_BOT_API_KEY` authentication
- **LINE Bot User Registration**: Fixed parameter name (`displayName` → `lineDisplayName`) and username validation logic
- **API Key Conflict**: Generated independent API Keys for Discord Bot and LINE Bot to avoid service identification conflicts
- **Webhook Forwarding**: Added webhook proxy in Backend to forward LINE webhook requests to LINE Bot service

#### New Features
- **Admin Dashboard v2**: Added simplified Python admin dashboard (Pure HTTP requests)
- **Signal Filter**: Added currency pair, timeframe, and direction filters to Admin Dashboard signal page
- **Scheduled Signal Service**: Added `scheduledSignalService.js` to support automated signal generation

#### Improvements
- **User Management**: Backend now displays Discord and LINE users
- **Service Architecture**: Strengthened API authentication mechanism between microservices

---

<div align="center">

**AIFX v2** - *Empowering Traders with AI*

Made with ❤️ by AIFX Team

[GitHub](https://github.com/LazOof69/AIFX_v2) •
[Report Issue](https://github.com/LazOof69/AIFX_v2/issues)

</div>
