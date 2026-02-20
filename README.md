# open_trade_prediction
Analyze trading discussions from Reddit, Telegram, and Twitter to generate actionable buy/sell signals with ML-powered predictions.

Scope of this project is to do senytinal analysis based on reddit groups and activities and provide sentinal analysis


```
┌─────────────┐    ┌─────────────┐    ┌─────────────┐    ┌─────────────┐
│   Reddit    │    │  Telegram   │    │   Twitter   │    │  Other      │
│   Posts     │    │  Channels   │    │   Posts     │    │  Sources    │
└──────┬──────┘    └──────┬──────┘    └──────┬──────┘    └──────┬──────┘
       │                  │                  │                  │
       └──────────────────┴──────────────────┴──────────────────┘
                          │
                          ▼
              ┌─────────────────────┐
              │  Data Collection    │  ← social_collector.py
              │  (Every hour/day)   │
              └──────────┬──────────┘
                         │
                         ▼
              ┌─────────────────────┐
              │  PostgreSQL DB      │  ← sisu_trade_analysis schema
              │  (Raw + Processed)  │
              └──────────┬──────────┘
                         │
                         ▼
              ┌─────────────────────┐
              │  Signal Generation  │  ← signal_generator.py
              │  ML Analysis        │
              │  Scoring Algorithm  │
              └──────────┬──────────┘
                         │
                         ▼
              ┌─────────────────────┐
              │  Pending Signals    │  ← Waiting for YOUR approval
              │  (Active/Pending)   │
              └──────────┬──────────┘
                         │
         ┌───────────────┼───────────────┐
         │               │               │
         ▼               ▼               ▼
    ┌─────────┐    ┌─────────┐    ┌─────────┐
    │ Approve │    │ Reject  │    │ Execute │
    │ (Queue) │    │ (Drop)  │    │ (Track) │
    └─────────┘    └─────────┘    └─────────┘
```
## ✨ Key Features

| Feature | Description |
|---------|-------------|
| **Social Monitoring** | Reddit (wallstreetbets, stocks, crypto), Telegram channels |
| **Sentiment Analysis** | Real-time bullish/bearish scoring |
| **ML Predictions** | Price direction prediction with confidence |
| **Smart Signals** | Buy/Sell/Watch with entry/exit prices |
| **User Control** | Manual approve/reject required (no auto-trading) |
| **Notifications** | Email, Telegram, webhook alerts |
| **P&L Tracking** | Track performance of executed signals |
