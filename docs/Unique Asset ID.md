# Unique Asset ID

A Unique Asset Identifier based on [Universal Asset ID of Trust Wallet](https://developer.trustwallet.com/developer/listing-new-assets/universal_asset_id). It's network agnostic and provides a way to uniquely identify tokens or coins in different networks.

It allows to identify any kind of network (blockchain, bank network, card network, etc) and token (fiat currencies or cryptocurrencies).

There is a list of all assets in [JSON format](../data/unique-asset.json).

## Params
- `n` - network (require): Network's name (blockchain, bank network, etc).
- `t` - token (require): This is the contract address of token, when possible, or th [ISO 4217](https://en.wikipedia.org/wiki/ISO_4217) for fiat currencies, or the most used name in the network

## Format
The format is:
```
n{network}_t{token}
```

## Examples

- USDC (Binance Smart Chain - BEP20): nbep20_t0x8AC76a51cc950d9822D68b83fE1Ad97B32Cd580d
- USDC (Solana - SOL): nsol_tEPjFWdd5AufqSSqeM2qN1xzybapC8G4wEGGkZwyTDt1v
- USDT (Tron - TRC20): ntrc20_tTR7NHqjeKQxGTCi8q8ZY4pL8otSzgjLj6t
- BTC (Bitcoin): nbitcoin_tBTC
- BTC (Lightning Network): nlightningnetwork_tBTC
- ARS (Bank Argentina): nbank-arg_tARS 
- USD (Bank Argentina): nbank-arg_tUSD
