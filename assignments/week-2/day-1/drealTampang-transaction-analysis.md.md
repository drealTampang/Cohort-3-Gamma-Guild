
# Week 2 – Blockchain & Web3 Deep Dive (Combined)
### By drealTampang

## Ethereum Transaction Analysis: 0xa93bc349561d1f3d834b3c645864a3cb618be747ef4ec66d71c6a5512eeafff6

## 1. Basic Information

* **Transaction Hash:** `0xa93bc349561d1f3d834b3c645864a3cb618be747ef4ec66d71c6a5512eeafff6` ([Etherscan](https://etherscan.io/tx/0xa93bc349561d1f3d834b3c645864a3cb618be747ef4ec66d71c6a5512eeafff6?utm_source=chatgpt.com))
* **Status:** Success
* **Timestamp:** December 17, 2019, 14:19:58 UTC
* **Block Number:** 9,120,962
* **Number of Confirmations:** Deeply confirmed (large number of confirmations due to transaction age)

## 2. Parties Involved

* **Sender:** `0x10aab4B0EF76AA2AC9b5909e671517a1171B050E` — **EOA (Externally Owned Account)**
* **Receiver / Interacted Contract:** `0x39AA39c021dfbaE8faC545936693aC917d5E7563` — **cUSDC token contract (Compound v2)**
* **Borrower (liquidated):** `0x39bDe2F9254cfEf7d0487a27E107Ef6C1685e44c`
* **Collateral cToken:** `0x4Ddc2D193948926D02f9B1fE9e1daa0718270ED5` — cETH

## 3. Value & Fees

* **Value Transferred (ETH):** 0 ETH
* **Tokens Transferred:**

  * **USDC:** 218,213.95672 USDC (from sender to cUSDC contract)
  * **cETH:** 88,730.60278869 cETH (from borrower to sender)
* **Transaction Fee:** 0.05980989189169152 ETH (~$262.42 at the time)
* **Gas Price:** 102.29981184 Gwei
* **Gas Limit:** 891,000
* **Gas Used:** 584,653 (~65.62% of the limit)

## 4. Technical Details

* **Method Called:** `liquidateBorrow(address borrower, uint256 repayAmount, address cTokenCollateral)`
* **Input Data Analysis:**

  * `borrower`: `0x39bDe2F9254cfEf7d0487a27E107Ef6C1685e44c`
  * `repayAmount`: 218,213.95672 USDC (decimal)
  * `cTokenCollateral`: `0x4ddc2d193948926d02f9b1fe9e1daa0718270ed5` (cETH)
* **Events Emitted / Logs:** Two major token transfers: USDC in, cETH out

## 5. Analysis

**Purpose:** This transaction was a **liquidation** on Compound v2. The sender repaid part of a borrower's debt in USDC and received the borrower's collateral (cETH).

**Gas Price Reasonableness:** 102 Gwei is high but justified due to the MEV opportunity. The transaction did not use the full gas limit, showing a conservative allocation.

**Potential Gas Savings:** Possibly, but reducing gas price risks losing the liquidation. The gas limit was overestimated, which is common to avoid out-of-gas errors.

**Sender Insights:** Likely an account or bot running liquidation strategies with significant capital. Able to handle large USDC repayments (~218k USDC), suggesting experience with DeFi operations.

**Borrower / Receiver Insights:** The borrower was undercollateralized, triggering the liquidation. The large size indicates a substantial position in ETH collateral and USDC debt.

## 6. Broader Context and Lessons

* **DeFi Risk:** Over-leveraging can trigger liquidation.
* **Opportunities for Bots:** Liquidation bots profit from repaying undercollateralized debt.
* **Protocol Mechanics:** Compound v2 incentivizes external actors to maintain protocol solvency.
* **Gas Strategy:** High-value MEV transactions justify premium gas payments.

**References:**

* [Etherscan Transaction Link](https://etherscan.io/tx/0xa93bc349561d1f3d834b3c645864a3cb618be747ef4ec66d71c6a5512eeafff6?utm_source=chatgpt.com)
* [Compound Docs](https://docs.compound.finance/v2/comptroller/?utm_source=chatgpt.com)
* [MEV Liquidation Analysis](https://thinkingchain.xyz/blog/mev-v1/mev-1-08-compound-v2-liquidation?utm_source=chatgpt.com)
