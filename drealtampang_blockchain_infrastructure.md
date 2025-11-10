# **Week 1 – Day 2: Blockchain Infrastructure & Distributed Ledger Research**

**Student Name:** Drealtampang  
**Date:** November 7, 2025  
**Tweet Link:** [https://x.com/jamespamni/status/1986817826058108931](https://x.com/jamespamni/status/1986817826058108931)
**Microsoft Visual Studio Method**

---

## **Part One – Blockchain Infrastructure Research**

### **What Is Blockchain Infrastructure**

**Technical Definition:** The foundational combination of hardware, software, nodes, and consensus algorithms that keep a blockchain running without central oversight.  

**Analogy:** It is like a national postal network — post offices are nodes, delivery routes are peer-to-peer connections, and postal rules are consensus protocols.  

**Economic Perspective:** A self-sustaining ecosystem of participants who store, verify, and secure a shared ledger for financial or reputational rewards rather than centralized control.

---

### **Representative Blockchains**

**Bitcoin (BTC)**  
Full nodes store and verify the entire ledger; SPV nodes (Simplified Payment Verification) rely on headers; and mining nodes compete to add blocks.  
Hardware typically needs a 4-core CPU, 8 GB RAM, and 500 GB disk space.  
Consensus mechanism: **PoW – Proof of Work.** Miners expend computational power solving puzzles to secure the network.  
*Analogy:* A global lottery in which the winner earns the right to add the next page of history.  
Rewards come as block rewards and transaction fees; wasted electricity acts as a deterrent against cheating.  
Average block time ≈ 10 minutes, throughput 3–7 TPS, finality around one hour.

---

**Ethereum (ETH)**  
Nodes may be full, light, or archive nodes.  
Clients include Geth (Go), Nethermind (C#), and Besu (Java).  
Consensus mechanism: **PoS – Proof of Stake.** Validators lock 32 ETH and take turns producing or attesting to new blocks.  
*Analogy:* A cooperative where shareholders vote and earn dividends for honest work.  
Rewards include gas fees and staking revenue; dishonest validators can lose their stake (“slashing”).  
Average block time ≈ 12 seconds with ≈ 30 TPS and 12-minute finality.

---

**Solana (SOL)**  
Node types include validators, RPC nodes, and archive nodes; hardware is demanding (12-core CPU, 128 GB RAM, 1 Gbps link).  
Consensus uses **PoH + PoS – Proof of History plus Proof of Stake.**  
*Analogy:* A train timetable where each carriage (timestamp) locks its position before departure, eliminating delays.  
Validators earn SOL rewards and can be jailed for downtime. Block time ≈ 0.4 seconds, throughput ≈ 3 000 TPS, finality ≈ 2 seconds.

---

**Polkadot (DOT)**  
Consensus mechanism: **NPoS – Nominated Proof of Stake.** Validators secure the relay chain while collators produce blocks for parachains.  
*Analogy:* A federal parliament where each state (parachain) sends delegates (collators) to a central senate (relay chain).*  
Average block time ≈ 6 seconds with parallel processing across parachains; validators earn DOT rewards, and malicious actors can be slashed.

---

**Avalanche (AVAX)** – less popular example  
Consensus follows the Avalanche Protocol based on random sampling and network voting until agreement emerges.  
*Analogy:* Neighbours poll each other repeatedly until everyone agrees on what happened.*  
Finality is typically under a second, ≈ 4 500 TPS, and validators stake AVAX with slashing for misconduct.

---

**Cardano (ADA)** – less popular example  
Consensus mechanism **Ouroboros PoS** relies on random slot leaders who produce blocks while others verify.  
*Analogy:* Each student takes turns reading while classmates check for mistakes.*  
Designed with academic rigour and formal proofs of security. Block time ≈ 20 seconds, throughput ≈ 250 TPS, finality ≈ 1 minute.

---

### **Blockchain Performance Overview**

| Blockchain | Consensus | Avg Block Time | TPS | Finality | Validator Type | Energy Use |
|-------------|------------|---------------|------|-----------|----------------|-------------|
| Bitcoin | PoW | 10 min | 3–7 | 60 min | Miners | High |
| Ethereum | PoS | 12 s | 30 | 12 min | Stakers | Low |
| Solana | PoH + PoS | 0.4 s | 3 000 | 2 s | Validators | Medium |
| Polkadot | NPoS | 6 s | High | 1 min | Validators/Collators | Low |
| Avalanche | Avalanche Proto. | <1 s | 4 500 | <2 s | Validators | Low |
| Cardano | Ouroboros PoS | 20 s | 250 | 1 min | Validators | Low |

---

### **Key Takeaways**

- Consensus design balances security and speed much like cash (vs) credit payments.  
- Heavy hardware requirements can reduce true decentralisation.  
- Layer-0 and multi-chain models (such as Polkadot and Avalanche) boost scalability through parallel processing.  
- Proof of Stake models are rapidly replacing Proof of Work for efficiency and sustainability.  

---

## **Part Two – Distributed Ledger Technology vs Blockchain**

### **Distributed Ledger Technology (DLT)**

**Definition 1:** A shared digital database replicated across multiple participants and kept in sync without a central administrator.  
**Definition 2:** A peer-to-peer system where consensus protocols guarantee data integrity across nodes.  
**Analogy:** A neighbourhood diary where every home keeps an identical copy and entries change only when everyone agrees.

---

### **Blockchain**

**Definition 1:** A DLT that structures data into cryptographically linked blocks forming an immutable chain.  
**Definition 2:** A public log of transactions ordered by time and protected by hashing and consensus.  
**Analogy:** A chain of sealed containers where breaking one seal alerts everyone to tampering.  

---

### **Comparison Between DLT and Blockchain**

| Aspect | DLT (General) | Blockchain (Specific Type of DLT) | Example |
|---------|----------------|----------------------------------|----------|
| Data Structure | Graph or DAG | Sequential blocks | IOTA vs Bitcoin |
| Consensus | Voting or BFT | PoW/PoS | Hashgraph vs Ethereum |
| Permissions | Often private | Usually public | Corda vs Bitcoin |
| Immutability | Optional | Built-in | Corda allows updates |
| Speed | Higher | Moderate | Hashgraph faster than PoW |
| Use Cases | Enterprise data sharing | Open token economies | Supply chain vs cryptocurrency |

---

### **Non-Blockchain DLT Examples**

- **IOTA (Tangle):** Transactions confirm two previous ones in a Directed Acyclic Graph — like citizens signing each other’s forms for approval.  
- **Hedera Hashgraph:** Uses “gossip about gossip” communication for fast Byzantine agreement and fair ordering.  
- **Corda (R3):** Permissioned DLT for banks — only involved parties see their transactions, similar to private notaries.  

---

### **Deep Analysis**

Choosing between blockchain and DLT is like choosing between a public court and a private arbitration panel.  
Blockchains offer transparency and security at the cost of speed, while DLTs prioritise privacy and efficiency for trusted participants.  
Hybrid models combining both traits will likely dominate future enterprise solutions.

---

## **Part Three – NFTs and Fungible Tokens**

### **Fungible Tokens**

**Definition 1:** Digital tokens where each unit is identical and interchangeable (e.g., 1 ETH = 1 ETH).  
**Definition 2:** A cryptographic representation of value that can be divided and exchanged freely.  
**Analogy:** Like bottled water of the same brand and size — any bottle is equally acceptable.  
Common standards include ERC-20 (Ethereum), BEP-20 (Binance Smart Chain), and SPL (Solana).  
Types include utility, governance, stablecoins, and reward tokens.

---

### **Non-Fungible Tokens (NFTs)**

**Definition 1:** Unique tokens that prove ownership of specific digital or physical assets.  
**Definition 2:** Immutable records of authenticity and provenance stored on a blockchain.  
**Analogy:** A concert ticket with your seat number — it cannot be swapped for another.  
Technical standards include ERC-721 and ERC-1155; metadata is stored on-chain or via IPFS (InterPlanetary File System).  
Fractional NFTs (F-NFTs) enable shared ownership of assets such as art or real estate, similar to owning shares in a building.

---

### **How NFTs and Tokens Transform Physical Assets**

| Concept | Analogy | Explanation |
|----------|----------|--------------|
| Digital Ownership | Receipt that never fades | Blockchain records immutable proof of ownership |
| Asset Tokenisation | Turning a house into shares | Each token represents fractional rights |
| Programmable Royalties | A book that pays its author each resale | Smart contracts automate royalties |
| Global Markets | 24/7 auction house | NFT marketplaces operate without borders |

---

### **Real-World Case Studies**

| Project | Description | Physical Link | Blockchain |
|----------|--------------|---------------|-------------|
| OpenSea | Marketplace for NFTs | Digital art and collectibles | Ethereum |
| Axie Infinity | Play-to-earn game | Virtual creatures with real value | Ronin |
| Propy | Tokenised property sales | Real-estate deeds on-chain | Ethereum |
| VeChain | Authenticity tracking | Luxury goods supply chains | VeChainThor |
| Audius | Music streaming via tokens | Musician royalties | Solana / Ethereum |

---

### **Comparison – Physical vs Digital Ownership**

| Feature | Physical Ownership | Digital Ownership (NFT / Token) |
|----------|-------------------|--------------------------------|
| Verification | Paper documents | Cryptographic proof |
| Transfer Speed | Days or weeks | Seconds |
| Cost | Lawyers and agents | Network fees only |
| Storage | Physical space | Digital wallet |
| Fraud Risk | Forgery possible | Nearly impossible |
| Divisibility | Hard | Easy through F-NFTs |
| Programmability | Manual contracts | Automatic via smart contracts |

---

### **New Economic Models and Creator Economy**

- Direct monetisation lets artists and creators earn without intermediaries.  
- Programmable royalties ensure perpetual compensation for resales.  
- Decentralised Autonomous Organisations (DAOs) allow communities to govern collectively.  
*Analogy:* Musicians own their record label while fans own shares in its success.

---

### **Future of Ownership**

NFTs and tokenisation blur the line between physical and digital rights.  
Art, property, and data may all exist as tradable tokens within a decade.  
Regulatory clarity and cybersecurity remain crucial, but tokenised ownership will likely redefine markets as the printing press once redefined information.

---

## **Glossary of Acronyms**

| Acronym | Meaning |
|----------|----------|
| PoW | Proof of Work |
| PoS | Proof of Stake |
| PoH | Proof of History |
| NPoS | Nominated Proof of Stake |
| DLT | Distributed Ledger Technology |
| NFT | Non-Fungible Token |
| TPS | Transactions Per Second |
| IPFS | InterPlanetary File System |
| DAO | Decentralised Autonomous Organisation |
| F-NFT | Fractional Non-Fungible Token |

---

## **References**

1. Coinbase – “Blockchain Infrastructure Basics.”  
2. Ethereum.org – “Ethereum Clients & Validators.”  
3. Solana Documentation – “Cluster Architecture and Consensus.”  
4. Polkadot Network Docs – “Relay Chain and Parachains.”  
5. Avalanche Documentation – “Avalanche Consensus Protocol.”  
6. Cardano.org – “Ouroboros Protocol.”  
7. Investopedia – “Distributed Ledger Technology (DLT).”  
8. Consensus.com – “Blockchain vs DLT.”  
9. CoinDesk – “What Are NFTs and How They Work.”  
10. VeChain.org – “Supply Chain Applications.”  
11. Propy.com – “Real Estate on Blockchain.”  
12. Audius.co – “Web3 Music Ownership.”  
