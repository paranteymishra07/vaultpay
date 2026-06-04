# VaultPay

A local EVM escrow payment dApp using virtual ERC20 tUSD on Hardhat.

## What it does

- Mint virtual tUSD from a faucet
- Approve VaultPay to spend your tUSD
- Create escrow payments with a deadline and optional memo
- Recipients can claim payments before the deadline
- Payers can cancel and recover funds after the deadline

## Stack

- Solidity + Hardhat (local chain, chain ID 31337)
- TypeScript tests with Hardhat + ethers
- React + Vite + wagmi + viem frontend

## Setup

### 1. Install dependencies

```bash
npm install
```

### 2. Compile contracts

```bash
npm run compile
```

### 3. Run tests

```bash
npm run test
```

All 9 tests pass covering: create, claim, cancel, authorization checks, deadline enforcement, and edge cases.

### 4. Run the local stack (3 terminals)

**Terminal 1 — Hardhat node:**
```bash
npm run node
```

**Terminal 2 — Deploy contracts:**
```bash
npm run deploy:local
```
Copy the printed `TOKEN_ADDRESS` and `VAULTPAY_ADDRESS` into `frontend/src/config.ts`.

**Terminal 3 — Frontend:**
```bash
cd frontend
npm install
npm run dev
```

Open http://127.0.0.1:5173/

### 5. MetaMask setup

- Add custom network: RPC `http://127.0.0.1:8545`, Chain ID `31337`, Symbol `ETH`
- Import a Hardhat test account private key from the `npm run node` output

## Screenshot

![VaultPay UI](screenshot.png)
