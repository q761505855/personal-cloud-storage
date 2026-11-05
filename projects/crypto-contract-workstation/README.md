# Crypto Contract Workstation Storage

Project ID: `crypto-contract-workstation`

Root: `projects/crypto-contract-workstation/`

## User configuration

`config/` stores the project's archived user preferences. Export/import validation is owned by the workstation. Configuration is separate from historical market data.

## Historical data

`data/market-history/` stores historical market archives. New archives use one-minute source candles; other chart periods are computed by the application. Planned layout:

```text
data/market-history/<symbol>/1m/<year>/<month>.json.gz
```

Ordinary trade prices and mark prices remain distinguishable inside each archive. The project manifest records paths, sizes and SHA-256 checksums. Reads and writes must preserve other months and other projects.

Directory placeholders are not data files and are not listed in the manifest. BTCUSDT 1m data for September 2025 is available: 43,200 trade candles and 43,200 mark-price candles, downloaded from official archives and verified through a cloud readback. User configuration is uploaded separately by the application.