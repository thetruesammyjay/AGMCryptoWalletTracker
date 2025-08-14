# AGM Crypto Wallet Tracker Bot - JavaScript File Structure

```
crypto-wallet-tracker-bot/
│
├── README.md
├── package.json
├── .env.example
├── .gitignore
├── index.js                    # Main bot entry point
│
├── src/
│   ├── bot.js                  # Telegram bot setup and handlers
│   ├── config.js               # Configuration settings
│   │
│   ├── commands/
│   │   ├── start.js           # /start command
│   │   ├── help.js            # /help command
│   │   ├── track.js           # /track command
│   │   ├── balance.js         # /balance command
│   │   └── analyze.js         # /analyze command (scam detection)
│   │
│   ├── services/
│   │   ├── bitcoin.js         # Bitcoin API calls
│   │   ├── ethereum.js        # Ethereum API calls
│   │   ├── solana.js          # Solana API calls
│   │   ├── tron.js            # USDT TRC20 API calls
│   │   └── binance.js         # USDT BEP20 API calls
│   │
│   ├── utils/
│   │   ├── validator.js       # Address validation
│   │   ├── formatter.js       # Format numbers and messages
│   │   ├── scamDetector.js    # Simple scam detection logic
│   │   └── database.js        # Simple JSON file database
│   │
│   └── data/
│       ├── users.json         # User data storage
│       ├── wallets.json       # Tracked wallets
│       └── scamlist.json      # Known scam addresses
│
├── tests/
│   ├── api.test.js           # Test API connections
│   └── commands.test.js      # Test bot commands
│
└── docs/
    └── API_KEYS.md           # How to get API keys
```

## Simple Architecture Overview

### Main Files
- **index.js**: Entry point that starts the bot
- **src/bot.js**: Main bot logic and command routing
- **src/config.js**: All configuration and API keys

### Commands (Individual files for each bot command)
- Simple, focused functions for each Telegram command
- Easy to understand and modify

### Services (One file per blockchain)
- **bitcoin.js**: Get BTC balance and transactions
- **ethereum.js**: Get ETH balance and transactions  
- **solana.js**: Get SOL balance and transactions
- **tron.js**: Get USDT TRC20 data
- **binance.js**: Get USDT BEP20 data

### Utils (Helper functions)
- **validator.js**: Check if addresses are valid
- **formatter.js**: Make data look nice for users
- **scamDetector.js**: Simple scam detection rules
- **database.js**: Save/load data from JSON files

### Data Storage (Simple JSON files)
- No complex database setup needed
- Easy to understand and backup
