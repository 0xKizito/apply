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

- ** Oracles:** Chainlink or RedStone (for RWA price and metadata feeds)


**Core Components (for MVP):**

1. **Offchain Routing Engine (Core):**

  - Computes optimal multi-path routes between two tokenized RWAs using available liquidity sources and stable settlement tokens (synthetic pairing via USDC/USDT). 

  - Considers price, slippage, gas, and counterparty constraints.

  - Returns an executable route (sequence of adapters + onchain settlements).

3. **RWA Token Module (Stub Version):**

Smart contract interfaces that stimulate RWA tokens with metadata standards (ISIN, issuer info, etc) for testing RWA pair listings and swaps.

4. **Liquidity Aggregator (Prototype):**

A module that aggregates liquidity from multiple internal orderbooks, paving the way for future integration with external DEXs or parachain liquidity sources. 


**UI Mockups (for MVP):**

- Minimalist orderbook interface 
- Data models / API specifications of the core functionality
- What your project is *not* or will *not* provide or implement
  - This is a place for you to manage expectations and clarify any limitations

### 🧩 Ecosystem Fit

Help us locate your project in the Polkadot landscape and what problems it tries to solve by answering each of these questions:

- Where and how does your project fit into the ecosystem?
- Who is your target audience?
- What need(s) does your project meet?
- Are there any other projects similar to yours in the Polkadot ecosystem?
  - If so, how is your project different?
  - If not, why might such a project not exist yet?

> **Note**: We prioritize projects building on Plaza/Polkadot Hub, games, and DeFi applications, though all types of projects will be considered.

## 👥 Team

- **Team Name:** Name of your team. If you apply as a legal entity, please use its name.
- **Contact Name:** Full name of the contact person in your team
- **Contact Email:** Contact email
- **Website:** Your website, GitHub org, blog, or similar

### Team members

Please list the legal name of all grant beneficiaries. Solo developers (1-person teams) are eligible for funding.

#### LinkedIn Profiles (if available)

- https://www.linkedin.com/{person_1}
- https://www.linkedin.com/{person_2}

### Team Code Repos

- https://github.com/{your_organisation}/{project_1}
- https://github.com/{your_organisation}/{project_2}

Please also provide the GitHub accounts of all team members:

- https://github.com/{team_member_1}
- https://github.com/{team_member_2}

### Team's experience

Please describe the team's relevant experience, including any previous blockchain projects or contributions to the ecosystem.

## 📊 Development Status

If you've already started implementing your project, please provide a link and a description of the code. Otherwise, please provide some documentation on the research and other work you have conducted before applying.

## 📅 Development Roadmap

This section should break the development roadmap down into milestones and deliverables. Since these will be part of the agreement, please describe *the functionality we should expect in as much detail as possible*, plus how we can verify and test that functionality.

**Important notes:**
- Each milestone is capped at **$5,000 USD**
- Milestones must be delivered within **3 months** of approval
- The maximum grant amount is **$10,000 USD** per application (up to **$15,000 USD** per project in exceptional cases)
- You will only receive payment after successful milestone delivery

### Overview

- **Estimated Duration:** Duration of the whole project (maximum 3 months)
- **Full-Time Equivalent (FTE):**  Average number of full-time employees working on the project
- **Total Costs:** Requested amount in USD for the whole project (maximum $10,000 USD)

> Note that deliverables 0a to 0d are mandatory. Please adapt their specification to your project.

| Number | Deliverable | Specification |
| -----: | ----------- | ------------- |
| 0a. | License | Apache 2.0 / GPLv3 / MIT / Unlicense |
| 0b. | Documentation | We will provide both **inline documentation** of the code and a basic **tutorial** that explains how a user can... |
| 0c. | Testing and Testing Guide | Core functions will be fully covered by comprehensive unit tests to ensure functionality and robustness. In the guide, we will describe how to run these tests. |
| 0d. | Article | We will publish an **article** that explains what was done/achieved as part of the grant. |
| 1. | Feature X | We will create a feature that will... (Please describe in detail) |
| 2. | Feature Y | The Y feature will... (Please describe in detail) |
| 3. | Feature Z | The Z feature will... (Please describe in detail) |

### 💰 Budget Breakdown

Please provide a breakdown of your budget by milestone:

| Milestone | Deliverables | Cost (USD) | Estimated Completion |
| --- | --- | --- | --- |
| 1 | Features X, Y | $5,000 | 1.5 months |
| 2 | Feature Z | $5,000 | 1.5 months |
| **Total** | | **$10,000** | **3 months** |

Make sure you show clearly what the funding is going towards (e.g. 30 hours of a full time employee at $X / hour).

## 🔮 Future Plans

Please include:

- How you intend to continue development after the Fast-Grant
- Any plans for seeking additional funding (other grants, VC funding, etc.)
- Your vision for the project's growth and impact in the Polkadot ecosystem

## ℹ️ Additional Information

Here you can add any additional information that you think is relevant to this application, such as:

- Work you have already done
- If there are any other teams who have already contributed to the project
- Other funding you may have applied for

Remember that the Fast-Grants Programme is designed as a first step for promising projects. We're looking for projects that can continue to grow beyond this initial funding.