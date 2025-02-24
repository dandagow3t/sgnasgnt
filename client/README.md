
# Liquidity Management

## Configurations
### Generate payer wallet
```
solana-keygen new --outfile payer.json
```

Provision wallet with SOL for fees and WSOL for liquidity.

### Configure Pool
Based on default configurations, the pool is SOL-USDC, 8sLbNZoA1cfnvMJLPfp98ZLAnFSYCFApfJKMbiXNLwxj

https://solscan.io/account/8sLbNZoA1cfnvMJLPfp98ZLAnFSYCFApfJKMbiXNLwxj

But if you want to use another pool, you can change the mint0, mint1 and amm_config_index in client_config.ini.

### Open any number of positions in configured Pool in a specific price range

`cargo run open-position --with-metadata --is-base-0 <lower_price> <upper_price> <liquidity>`

```bash
cargo run open-position --with-metadata --is-base-0 173.111627 173.180482 40000000
```

### Close all positions in configured Pool and remove the liquidity.

```bash
cargo run remove-all-liquidity
```

### Sample scenario

```
cargo run open-position --with-metadata --is-base-0 173.111627 173.180482 40000000
cargo run open-position --with-metadata --is-base-0 170.111627 170.180482 40000000
cargo run remove-all-liquidity
```
