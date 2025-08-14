# 🔐 AGM Crypto Wallet Tracker Bot

A simple Telegram bot for tracking cryptocurrency wallets and detecting potential scams. Built with JavaScript for AGM Tech Pulse.

**Telegram Bot**: [@AGMCryptoWalletTrackerBot](https://t.me/AGMCryptoWalletTrackerBot)

## 🚀 Features

- **Check Wallet Balance**: Get current balance for any supported wallet
- **Transaction Count**: See total number of transactions
- **Scam Detection**: Basic scam risk assessment
- **Multi-Blockchain**: Supports BTC, ETH, SOL, USDT (TRC20 & BEP20)

## 💻 Supported Cryptocurrencies

- Bitcoin (BTC)
- Ethereum (ETH) 
- Solana (SOL)
- USDT on Tron (TRC20)
- USDT on Binance Smart Chain (BEP20)

## 🛠️ Tech Stack

- **Node.js** - JavaScript runtime
- **node-telegram-bot-api** - Telegram bot library
- **axios** - HTTP requests to blockchain APIs
- **JSON files** - Simple data storage

## 📦 Installation

### 1. Prerequisites
- Node.js 16+ installed
- Get API keys (see docs/API_KEYS.md)

### 2. Clone & Setup
```bash
git clone https://github.com/thetruesammyjay/crypto-wallet-tracker-bot.git
cd crypto-wallet-tracker-bot
npm install
```

### 3. Environment Setup
```bash
cp .env.example .env
```
Edit `.env` file:
```env
BOT_TOKEN=your_telegram_bot_token
ETHERSCAN_API_KEY=your_etherscan_key
BLOCKCYPHER_API_KEY=your_blockcypher_key  
TRONGRID_API_KEY=your_trongrid_key
BSCSCAN_API_KEY=your_bscscan_key
```

### 4. Run the Bot
```bash
npm start
```

## 🤖 Bot Commands

- `/start` - Welcome message
- `/help` - Show all commands
- `/balance <address>` - Get wallet balance
- `/track <address>` - Track a wallet  
- `/analyze <address>` - Check for scam risk

### Examples:
```
/balance 1A1zP1eP5QGefi2DMPTfTL5SLmv7DivfNa
/track 0xde0B295669a9FD93d5F28D9Ec85E40f4cb697BAe
/analyze TQn9Y2khEsLJW1ChVWFMSMeRDow5oREqLg
```

## 📁 Project Structure

```
src/
├── bot.js           # Main bot logic
├── config.js        # Settings and API keys
├── commands/        # Bot commands (/start, /help, etc.)
├── services/        # Blockchain API calls
├── utils/           # Helper functions
└── data/           # JSON data storage
```

## 🔧 Package.json

```json
{
  "name": "agm-crypto-wallet-tracker",
  "version": "1.0.0",
  "description": "Simple crypto wallet tracker for Telegram",
  "main": "index.js",
  "scripts": {
    "start": "node index.js",
    "dev": "nodemon index.js",
    "test": "jest"
  },
  "dependencies": {
    "node-telegram-bot-api": "^0.61.0",
    "axios": "^1.4.0",
    "dotenv": "^16.0.3"
  },
  "devDependencies": {
    "nodemon": "^2.0.22",
    "jest": "^29.5.0"
  }
}
```

## 🛡️ Simple Scam Detection

The bot checks for these red flags:
- Very high transaction count (>10,000)
- Address in known scam list
- Suspicious balance patterns
- Multiple small transactions (dust attacks)

**Risk Levels:**
- 🟢 **Low (0-30%)** - Normal wallet
- 🟡 **Medium (31-70%)** - Some suspicious activity  
- 🔴 **High (71-100%)** - Likely scam

## 🔑 Getting API Keys

### Required APIs:
1. **Telegram Bot Token**: Message @BotFather on Telegram
2. **Etherscan**: Free at etherscan.io/apis
3. **BlockCypher**: Free at blockcypher.com/dev
4. **TronGrid**: Free at trongrid.io
5. **BSCScan**: Free at bscscan.com/apis

See `docs/API_KEYS.md` for detailed instructions.

## 📊 Example Bot Responses

### Balance Check:
```
💰 Wallet Balance

Address: 1A1zP1eP5QGefi2DMPTfTL5SLmv7DivfNa
Network: Bitcoin (BTC)
Balance: 0.00000000 BTC ($0.00)
Transactions: 1,234
Risk Level: 🟢 Low (5%)
```

### Scam Analysis:
```
🔍 Scam Risk Analysis

⚠️ Medium Risk (65%)

Red Flags Found:
• High transaction volume
• Multiple dust transactions
• Similar to known patterns

Recommendation: Proceed with caution
```

## 🚀 Deployment

### Local Development:
```bash
npm run dev
```

### Production:
```bash
npm start
```

### Using PM2:
```bash
npm install -g pm2
pm2 start index.js --name crypto-bot
```

## 🧪 Testing

```bash
npm test
```

Test individual APIs:
```bash
node tests/api.test.js
```

## 📝 Contributing

1. Fork the repository
2. Create your feature branch
3. Make your changes
4. Test your changes
5. Submit a pull request

## 📞 Support

- **Company**: AGM Tech Pulse
- **Bot**: [@AGMCryptoWalletTrackerBot](https://t.me/AGMCryptoWalletTrackerBot)
- **Issues**: Create GitHub issue

## ⚠️ Disclaimers

- This is a basic scam detector, not 100% accurate
- Always do your own research before transactions
- API rate limits may apply
- Educational/informational purposes only

---

**🚀 Simple, Fast, Effective - Built for AGM Tech Pulse**
