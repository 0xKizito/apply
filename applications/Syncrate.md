# Syncrate Network

## 🌟 Project Overview

**Project Name:** Syncrate

**Tagline:** Modular cross-chain interoperability layer for tokenized real-world assets.

**Brief Description:**
**Syncrate** is an interoperability layer designed to connect fragmented real-world asset markets across multiple blockchains.
It enables seamless routing and liquidity flow between tokenized assets, by abstracting complex settlement and cross-chain communication behind a unified routing layer.

The MVP focuses on building the routing engine and adapter contracts that can query liquidity sources, compute efficient paths between RWA protocols, and execute synthetic settlements via stablecoin intermediaries. Syncrate’s mission is to simplify cross-market movement for users and developers, fostering a more connected and liquid RWA ecosystem.

**Relation to Polkadot:**
Polkadot’s multi-chain architecture and cross-consensus messaging (XCM) provide the ideal foundation for Syncrate’s interoperability goals.
By deploying on Moonbeam, Syncrate can leverage both EVM compatibility and native access to Polkadot’s cross-chain communication.

**Why We're Interested:** The team believes that tokenization are the most tangible path to real-world adoption of Web3, yet the current market is fragmented with assets sitting in isolated pools and chains.
Having spent years observing how liquidity fragmentation limits user participation and protocol growth, we’re motivated to build the routing infrastructure that bridges these isolated RWA ecosystems.

By building Syncrate on Polkadot (starting with Moonbeam), we can combine scalable interoperability with secure cross-chain messaging, positioning Polkadot as the core hub for multi-chain RWA settlement.

### 🔍 Project Details

**Technology Stack (MVP Phase):**

- **Smart Contracts:** Solidity (deployed on Moonbeam for EVM compatibility)

- **Backend Services:** Node.js & TypeScript (for routing logic, price feeds, and other management)

- **Database Layer:** PostgreSQL for offchain order indexing and historical data.

- **Frontend:** React + Next.js for web UI

- **Cross-chain Messaging:** XCM intergration/LayerZero or Axelar adapters (Phase 2) for interoperability testing

- **Oracles:** Chainlink or RedStone (for RWA price and metadata feeds)



**Core Components (for MVP):**

1. **Offchain Routing Engine (Core):**

  - Computes optimal multi-path routes between two tokenized RWAs using available liquidity sources and stable settlement tokens (synthetic pairing via USDC/USDT). 

  - Considers price, slippage, gas, and counterparty constraints.

  - Returns an executable route (sequence of adapters + onchain settlements).

2. **On-Chain Settlement & Adapter Contracts (Minimal):**

  - Lightweight contracts to perform final settlement steps onchain (e.g.,swap execution on a paired pool, cross-contract call orchestration).

  - Adapter contract interfaces that standardize interaction with integrated liquidity sources (DEXs, vaults, oracles on Moonbeam)

3. **Liquidity Adapter Layer (Prototype):**

  - Pluggable adapters for liquidity sources (internal test pools, simple AMM stubs, or partner DEXs) so the router can query depth and execution paths.

4. **RWA Metadata & Pricing Module:**

  - Offchain module that ingests RWA metadata (issuer, maturity, coupon, ISIN-like id) and price signals from oracles to inform routing decisions.

5. **Frontend Demo & Developer API:**

  - UI to submit a source and target RWA, view proposed routes, and simulate settlement.

  - REST APIs: /route, /quote, /execute, /markets, /metadata.



**UI Mockups (for MVP):**
The MVP will feature a minimal dashboard interface that demonstrates Syncrate's routing functionality. 
Users will be able to:

 - Connect a wallet (starting with Metamask via Moonbeam)

 - Select a source and destination RWA protocol/chain

 - View the optimal route, estimated cost and time

 - Execute a simple cross-protocol transer using test assets.



**Data Models / API Specifications:**

 - POST /route — payload: { from_asset, to_asset, amount, max_slippage } → response: { routes: [{ steps: [...] , estPrice, estFee }] }

 - POST /execute — payload: { selected_route, user_signature } → response: { tx_hashes, status }

 - GET /markets — list supported assets + metadata

 - GET /adapters — available liquidity adapters and their health/depth



**What the MVP is NOT (scope boundaries):**

 - **Not a custody layer / not holding user funds** - Settlement uses non-custodial on-chain calls.

 - **Not a full DEX/orderbook** — we do not implement a native matching engine for limit orderbooks on-chain during MVP.

 - **Not full multi-chain settlement** — cross-parachain/native bridging reserved for Phase 2.


### 🧩 Ecosystem Fit


**How we fit into the ecosystem:**
Syncrate fits into the RWA tokenization vertical, bringing interoperability and cross-chain routing to protocols already tokenizing real world assets.

**Target Audience:**
Our target audience includes tokenization protocols & institutions, onchain asset managers and crypto traders.

**The problem we're solving:**
Today, tokenized RWAs sit in isolated pools, making it difficult for investors and traders to move capital between asset classes and chains. 
Syncrate solves this problem by introducing a routing solution that connects this these fragmented ecosystems. 

**Our competitors:**
There is currently no direct competitors focused solely on interoperability for tokenized RWAs. While protocols like LayerZero, Axelar and Wormhole provide general cross-chain solutions, Syncrate is purpose-built for RWA liquidity. 
 
Other RWA projects compete for liquidity, Syncrate connects them


## 👥 Team

**Team Name:** Syncrate Labs

**Contact Name:** Kizito Chukwuma

**Contact Email:** kizitoweb3@gmail.com

**Blog:** https://medium.com/@syncrate

### Team members

Founder & CEO - Kizito Chukwuma

Founding CTO - Amaechi Okolobi

#### LinkedIn Profiles 

- https://www.linkedin.com/in/amaechi-okolobi-3b36811a6/

### Team Codes Repo

Repo will be available when we start building the MVP

**Kizito's Github:**
https://github.com/0xKizito

### Team's experience

**Kizito Chukwuma:**
Previously Operations Manager at Flutterwave, he streamlined fintech operations across Africa, scaling payment infrastructure for millions.
With 5+ years of experience in business development across diverse Web3 protocols including, CIAN Protocol and StakeToby, he’s passionate about DeFi and the next wave of tokenized economies. 

A B.Eng degree holder from the Federal University of Technology, Owerri (one of the most prestigious institutions in West Africa). He also holds an Oxford Blockchain Strategy certificate from the Oxford Saïd Business School.

**Amechi Okolobi:**
Solana Labs Cohort 3 and Ex. Head of Security at Chainlink Labs, Amaechi brings blockchain security and RWA tokenization expertise to Syncrate. He has worked with web3 protocols across the UAE and New York. 
Amaechi is also the founder of DeCentral Hub, a community of blockchain founders and developers. He is also the co-founder of Kova Network, a new and emerging computeFi protocol. 

## 📊 Development Status

We're still pre-MVP but has conducted extensive research on the RWA tokenization market and seen the need for an interoperability layer.

Our full research thesis can be found in our deck;
https://drive.google.com/file/d/1qq3qzZbRF-6fCL_reEDfHxeClBRkIv7L/view?usp=drivesdk


## 📅 Development Roadmap

### Overview

**Estimated Duration:** 8 weeks

**Full-Time Equivalent (FTE):** Two developers 

**Total Costs:** $6,500


| Number | Deliverable | Specification |
| -----: | ----------- | ------------- |
| 0a. | LICENSE file in repo | MIT license for all code and examples (permissive, grant-friendly). |
| 0b. | Repo docs, API spec, and a deployment README | We will provide an inline code docs + a short developer README.md and an Adapter Integration Guide covering how to write / plug adapters into the router. |
| 0c. | test/ + TESTING.md | Unit tests for core routing logic and adapter contracts; a brief testing guide describing how to run tests locally and on CI. |
| 0d. | Publishable article + short announcement thread | We will publish a public write-up (medium-style / Devpost) summarizing what was built, design choices, and how other devs can integrate. |
| 1. | Feature 1 - Offchain Routing Engine (core) | We will create a develop the core TypeScript routing engine that computes optimal asset routes. This would include REST endpoints (/route, /quote, /adapters) and serialization for execution payloads. |
| 2. | Feature 2 - Adapter Contracts & Interface | We will build Solidity adapter interface and deploy two prototype adapters (StableSettlementAdapter and TestAMMAdapter) on Moonbase Alpha. This includes adapter integration tests and ABI documentation. |
| 3. | Feature 3 - Frontend Demo & Developer API Docs| We will create a minimal React frontend that connects to Moonbase Alpha, displays simulated routes, and runs test executions. Finally, we'll publish OpenAPI docs and deployment instructions for developers. |

### 💰 Budget Breakdown


| Milestone | Deliverables | Cost (USD) | Estimated Completion |
| --- | --- | --- | --- |
| 1 | Routing engine | $4,500 | 3 weeks |
| 2 | Adapter Contracts & Tests | $1,000 | 2 weeks |
| 3 | Frontend Demo + API Docs | $600 | 2 weeks | 
| 4 | Article & final handoff | $400 | 1 week |
| **Total** | | **$6,500** | **8 weeks** |

- The largest chunk goes towards the routing engine (which is the core work)

- Budget covers developer time (2 devs part-time / or 1 full-time + part-time reviewer), testnet deployment costs, and small infra (CI, small cloud for indexer during testing).
No marketing/mainnet costs included.

## 🔮 Future Plans

- Once MVP is live, we plan to have the first pre-seed raise with select individuals and private communities. This raise will be capped at $100k and will be used for further protocol development, team hires and our first wave of marketing push.
We also plan one additional VC raise capped at $1.2m at a $10M valuation. 

- At mainnet, Syncrate will generate revenue from routing and transaction fees (0.30-0.50%), institutional API access, and cross-chain settlement services for RWA issuers.

- For our growth strategy, we will  partner with RWA protocols and on-chain asset managers to integrate routing.
Our core users will come from these partnerships / integrations. 

## ℹ️ Additional Information

- We've completed the ideology stage is now ready to build the MVP (once we secure this grant)

- At this stage, we've also finalized discussions with 3 launch partners that will be integrating Syncrate's routing solution both at testnet and when we launch the mainnet.
We've also onboarded Zeus (@zeusRWA on twitter) - a well known name in the RWA ecosystem - as an advisor. 

- We'll have 3 testnets, first a closed in-house testnet, then the first gated testnet with select individuals (incentivized) and finally a public testnet (will not be incentivized).
The public testnet will not be incentivized because we don't plan to build a community of farmers that provides minimal value and expect huge rewards. Nonetheless, we will reward contributors that stick and build with us.

A more detailed roadmap can be found in our deck; https://drive.google.com/file/d/1qq3qzZbRF-6fCL_reEDfHxeClBRkIv7L/view?usp=drivesdk

