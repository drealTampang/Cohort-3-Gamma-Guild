
## Week 2 Assignment: Blockchain & Web3 Deep Dive (Parts 1-5)

### 1. Consensus Mechanisms Deep Dive

#### 1. Proof of Work (PoW) Analysis

| Component | Explanation | Real-Life Analogy |
| :--- | :--- | :--- |
| **How PoW Works** | Miners compete by rapidly calculating billions of hashes to find a specific output hash (a "**nonce**") that meets a network difficulty target. This proves computational effort. | **A Global Lottery:** Everyone buys tickets (runs hashes) until one person finds the winning number (the correct nonce). |
| **Security Model** | Security is based on computational cost (hardware and electricity). A **51% attack** is prevented by the sheer cost of acquiring over half the network's hash power. | **The Cost of Gold:** To control the gold market, you'd need more than 50% of the world's mining capacity—an economically prohibitive investment. |
| **Trade-offs** | Pro: **Battle-tested security**, high immutability. Con: **Massive energy consumption** and limited scalability. | |

---

#### 2. Proof of Stake (PoS) Analysis

| Component | Explanation | Real-Life Analogy |
| :--- | :--- | :--- |
| **How PoS Works** | **Validators** lock up (**stake**) a native cryptocurrency to gain the right to propose and attest to blocks. They are chosen pseudo-randomly based on stake size. | **Shareholder Voting:** Security is based on economic investment. The more shares (stake) you own, the more influence (chance to validate) you have. |
| **Slashing** | The act of destroying a validator's stake as a **penalty for malicious behavior** (e.g., double-signing). | **A Security Deposit:** If a tenant (validator) breaks the lease (protocol rules), they lose their security deposit (stake) as a penalty. |
| **Trade-offs** | Pro: **Highly energy efficient**, better scalability potential. Con: Centralization risk if staking pools become too dominant (stake centralization). | |

---

#### 3. Comparative Analysis

| Feature | Proof of Work (PoW) | Proof of Stake (PoS) |
| :--- | :--- | :--- |
| **Security Model** | Computational/Physical: Security proportional to hardware investment. | Economic/Financial: Security proportional to staked capital. |
| **Energy Consumption** | **Very High** (Massive electricity consumption). | **Very Low** (Extremely energy efficient). |
| **Transaction Speed** | Low (Limited by fixed, slow block times, e.g., Bitcoin: 10 mins). | High (Faster block times, higher throughput). |
| **Entry Barrier** | High (Cost of specialized hardware + electricity). | Medium/High (Cost of capital stake, e.g., 32 ETH). |

---

### 2. Gas, Blocks & Confirmations

#### 1. Gas Economics & Analogy

| What is Gas? | Gas is the **unit of measure** for the computational effort required to execute an operation on the Ethereum Virtual Machine (EVM). |
| :--- | :--- |
| **Analogy:** | Gas is the **fuel** for the decentralized computer (the blockchain). The **Gas Limit** is the capacity of your fuel tank, and the **Gas Price** (in Gwei) is the price per gallon of fuel. |
| **Total Transaction Cost:** | $$\text{Gas Used} \times \text{Gas Price} = \text{Total Cost}$$ |

---

#### 2. Blocks Structure

| Block Component | Description |
| :--- | :--- |
| **Parent Block Hash** | The cryptographic link to the previous block, forming the chain's immutability. |
| **State Root** | The hash of the entire network's state (all balances, contract data) after the block's transactions are executed. |
| **Base Fee Per Gas** | The minimum price required to include a transaction, which is dynamically adjusted (**burned**) based on network congestion (EIP-1559). |
| **Transactions** | The bundled list of all transactions included in that block. |

---

#### 3. Confirmations and Finality

A **Confirmation** is when a transaction is included in a block, and subsequent blocks are added on top of it, making the reversal of the transaction increasingly unlikely.

| Scenario | Recommended Confirmations | Rationale |
| :--- | :--- | :--- |
| **General ETH Finality** | 12–15 Confirmations | Considered **highly secure** on Ethereum, making chain reorganization risk negligible. |
| **Major Exchanges (Deposits)** | 25–50 Confirmations | Centralized parties require extra security buffer against any remote possibility of a chain re-org before crediting large sums. |
| **NFT Sale/Minting** | 1 Confirmation | Transaction is functionally complete after the first block. Waiting for more is only necessary for the recipient/marketplace's internal security. |

---

### 3. Wallet Security & Types

#### 1. Custodial vs Non-Custodial Wallets

| Feature | Custodial (e.g., Binance, Coinbase) | Non-Custodial (e.g., MetaMask, Ledger) |
| :--- | :--- | :--- |
| **Key Ownership** | Third party (exchange/service) holds keys. | **You hold the private keys/seed phrase.** |
| **Control/Sovereignty** | Low (funds can be frozen). | **High** (full control, permissionless access). |
| **Recovery** | Easy (password reset via email/support). | **Solely based on Seed Phrase** (irreversible loss if seed is lost). |
| **Analogy** | **Bank Account:** You trust the bank with your money and keys. | **Physical Safe:** Only you hold the key; losing it means losing everything. |

---

#### 2. Hot vs Cold Wallets

* **Hot Wallet:** **Internet-connected** (e.g., MetaMask). High convenience, **higher risk** of malware/phishing. Used for small, frequent transactions ("spending money").
* **Cold Wallet:** **Offline storage** (e.g., Ledger, Trezor). Keys are stored on an air-gapped device. **Maximum security**. Used for large, long-term holdings ("the vault").

---

#### 3. Security Best Practices 🛡️

| Category | Security Checklist Item |
| :--- | :--- |
| **Seed Phrase Security** | ✅ Store the **Seed Phrase Offline** (never digital, screenshot, or cloud backup). Stamp into metal is ideal. |
| **Anti-Attack Vectors** | ✅ Always **manually verify the recipient address** before sending (protect against clipboard hijackers). |
| **Daily Practices** | ✅ **Revoke unnecessary token approvals** (permissions for dApps to spend your tokens) via an explorer. |
| **Allocation Strategy** | ✅ Use the **80/20 Rule**: 80% in Cold Storage (vault), 20% in Hot Wallet (spending). |

---

### 4. Testnets & Blockchain Explorers

#### 1. Testnets

* **Definition:** **Clones of the main blockchain (Mainnet)** used for safe, risk-free development and user practice.
* **Difference from Mainnet:** Use **faucet tokens** (like Sepolia ETH) that have **no real monetary value**. This allows developers to test smart contracts and users to practice wallets and dApps without financial risk.

---

#### 2. Blockchain Explorers (Etherscan Deep Dive)

* **Definition:** A web-based search engine that allows users to view real-time and historical data on all transactions, blocks, addresses, and smart contracts on a specific blockchain.
* **Analogy:** A blockchain explorer is the **Google Search for the entire public ledger.**
* **Critical Feature (for Security):** The **Token Approvals Checker** allows users to see and **Revoke** the permissions they've given contracts to move their assets, which is essential after interacting with new or complex dApps.

| Explorer | Associated Blockchain | Key Differences |
| :--- | :--- | :--- |
| **Etherscan** | Ethereum (ETH) | The standard template; highly developed features like Gas Tracker and Code Verification. |
| **Polygonscan** | Polygon (MATIC) | Identical UX to Etherscan, focused on Layer 2, low-cost EVM transactions. |
| **Solscan** | Solana (SOL) | Different UX; focuses on the non-EVM structure and rapid finality tracking (uses "signatures" instead of "hashes"). |

---

### 5. MEV (Maximal Extractable Value)

#### 1. Understanding MEV

| What is MEV? | The **maximum value** that can be extracted from block production through the **non-random inclusion, exclusion, and ordering** of transactions within a block. |
| :--- | :--- |
| **Who extracts it?** | **Searchers** (specialized bots) find the opportunities, and **Block Builders/Validators** collect the profit (bribes/priority fees). |
| **Analogy:** | MEV is like **insider trading** or finding the most profitable back-alley deal on Wall Street, but done transparently on a blockchain ledger. |

---

#### 2. How MEV Works (Attack Types)

| Attack Type | Mechanic | Impact on Users |
| :--- | :--- | :--- |
| **Front-Running** | A bot sees a pending transaction (e.g., a large DEX swap) and submits an identical transaction with a higher gas price to ensure it executes first, profiting from the immediate price movement the victim's trade causes. | The user gets a **worse execution price** (higher slippage). |
| **Sandwich Attack** | A bot places a **Buy** order **before** the victim's trade and a **Sell** order **after** the victim's trade, trapping and profiting from the victim's price impact. | The user **loses value** both when they buy and when they sell due to artificial price pressure. |

---

#### 3. MEV Solutions

* **Flashbots:** The dominant solution. Searchers send **private bundles** of transactions and bribes directly to a Block Builder, **bypassing the public mempool.**
    * **Benefit:** Eliminates gas wars and protects users from being seen and front-run by public mempool bots.
* **Proposer-Builder Separation (PBS):** A structural change on Ethereum that **separates the competitive building of the block (Builder)** from the final decision to publish it (**Proposer/Validator**), reducing centralization risk in MEV extraction.
* **Private Mempools:** Services that offer a dedicated, private submission channel, ensuring that your transaction is not viewable by MEV bots before it is mined.
