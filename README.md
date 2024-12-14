# Plaza Finance Auto Bot

## Description
This bot automates daily interactions with the Plaza Finance platform, including:

- Claiming tokens from the faucet.
- Creating Bond Tokens and Leverage Tokens with random deposit amounts.
- Redeeming 50% of Bond Tokens and Leverage Tokens.

The bot processes multiple wallets sequentially and can be run periodically.

---

## Register
- **Join**: https://testnet.plaza.finance/rewards/thtlP8i4fgzf
---

## Requirements

### Python Version
The bot requires **Python 3.7 or higher** due to its use of asynchronous syntax.

### Dependencies
Install the required Python packages:
```bash
pip install web3 requests colorama
```

---

## Setup Instructions

### 1. Clone the Repository
Clone the project from GitHub:
```bash
git clone https://github.com/airdropinsiders/plazafinance-auto-bot.git
cd plazafinance-auto-bot
```

### 2. Configuration Files

Create a file named `private_keys.txt` in the same directory as the script. This file should contain the private keys for the wallets you want to process, one per line.

**Example `private_keys.txt`:**
```
abcdef1234567890abcdef1234567890abcdef1234567890abcdef1234567890
1234567890abcdef1234567890abcdef1234567890abcdef1234567890abcdef
```

### 3. Script Execution
Run the script using:
```bash
python bot.py
```

---

## Features

### Faucet Claim
- Claims tokens from the Plaza Finance faucet.
- Handles rate-limiting errors gracefully.

### Unlimited Spending Approval
- Ensures unlimited approval for wstETH to the Plaza Finance contract.

### Token Creation
- Creates Bond Tokens and Leverage Tokens with random deposit amounts between 0.009 and 0.01 ETH.

### Token Redemption
- Redeems 50% of the balance of Bond Tokens and Leverage Tokens.

### Retry Mechanism
- Implements a retry mechanism for failed transactions, retrying up to 5 times with a delay between attempts.

### Logging
- Provides clear and color-coded logs for each step and transaction status.

---

## Bot Behavior
The bot processes each wallet in the following sequence:

1. Claims faucet tokens.
2. Ensures unlimited spending for wstETH.
3. Creates Bond Tokens with a random deposit amount.
4. Creates Leverage Tokens with a random deposit amount.
5. Redeems 50% of Bond Tokens.
6. Redeems 50% of Leverage Tokens.
7. Waits for 30 seconds before processing the next wallet.

---

## Common Issues and Troubleshooting

### 1. `private_keys.txt` Missing
If `private_keys.txt` is missing, the script will exit with an error message. Ensure the file exists and is populated with valid private keys.

### 2. Insufficient Gas Funds
Ensure each wallet has enough ETH for gas fees.

### 3. Transaction Errors
The bot retries failed transactions up to 5 times. Check the logs for detailed error messages.

### 4. API Errors
Rate-limiting or other API errors will be logged. Wait for the specified cooldown period and try again.

---

## Future Enhancements

- Add support for more token operations.
- Implement additional error-handling and alert mechanisms.
- Allow dynamic configuration of token amounts and retry policies.

---

## Disclaimer
This script interacts with decentralized finance (DeFi) platforms and requires private keys for operations. Use at your own risk and ensure you understand the implications of sharing private keys. Always test with small amounts before scaling up operations.
