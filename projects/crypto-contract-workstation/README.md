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

`manifest.json` starts empty. Directory placeholders are not data files and are not listed in the manifest. No user preferences or market archives have been uploaded yet.