# Python Demo for IzumiSwap (zkSync-Era) Token Exchange
* Supports swapping ETH -> USDC, USDC -> ETH, ETH -> USDT, USDT -> ETH

## Notice
* Special note: The USDT here is different from other Swap's USDT token contracts. It is a type of shared stablecoin pool based on USDC and will receive a special token called sLUSDT, with 18 decimals.

# Install dependencies
```bash
pip install -r requirements.txt
```

# Code
```python
from main import Izumi

# Your account private key or 12-word mnemonic seeds, auto check
your_account_key = ''

# Etherscan API key (not necessary)
# Register at https://etherscan.io/register to get it, but it's not required for this script
your_ether_scan_key = ''

# Slippage, default 0.5%. If you get a "too much request" error, please increase it, e.g., 0.01, or try when the mainnet gas fee is lower.
slippage = 0.005

# Amount to swap. For example, if coin_from is ETH and coin_to is USDC, it means swapping 0.0001 ETH to its equivalent in USDC. The exact amount depends on the current ETH price.
swap_amount = 0.0001

# The token to swap from
coin_from = 'eth'

# The target token to swap to
coin_to = 'usdc'

# To swap back to the original coin, just switch coin_from and coin_to
izm = Izumi(coin_from=coin_from,
            coin_to=coin_to,
            amount=swap_amount,
            account_key=your_account_key,
            scan_key=your_ether_scan_key,
            slippage=slippage
            )
izm.swap()
```

# Disclaimer: Please test with a small amount if you understand the code. I am not responsible for any financial losses due to swapping the entire amount at once.
