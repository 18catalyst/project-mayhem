# RugPulse

## Predictive Security Intelligence for Solana

> A real-time fraud-detection and risk-scoring platform for new Solana tokens, designed for human traders and autonomous trading agents.

| | |
| --- | --- |
| **Project status** | Proposal and technical validation |
| **Working title** | RugPulse |

## Contents

- [The Opportunity](#the-opportunity)
- [The Product](#the-product)
- [Risk Analysis](#risk-analysis)
- [What Makes It Different](#what-makes-it-different)
- [Human and Agent Products](#human-and-agent-products)
- [Proposed MVP](#proposed-mvp)
- [Commercial Model](#commercial-model)
- [Token Strategy](#token-strategy)
- [Why This Project Is Well Positioned](#why-this-project-is-well-positioned)
- [Proposed Next Step](#proposed-next-step)
- [References](#references)

## The Opportunity

Solana remains one of the busiest environments for launching and trading new crypto assets. At the time of this proposal, it had processed approximately **$62 billion in DEX volume over the preceding 30 days**, creating substantial demand for improved security and risk intelligence.[^1]

Existing token scanners generally identify static warning signs, such as retained mint authority, concentrated ownership or unlocked liquidity. However, many Solana scams operate through coordinated wallet behaviour, manipulated trading volume and rapid liquidity movements rather than malicious token code.

Our opportunity is to build a system that does not simply inspect a token once. It would continuously monitor its launch and attempt to identify fraudulent behaviour as it develops.

## The Product

RugPulse would operate as a predictive threat-intelligence platform for Solana.

Every newly launched token would receive updated risk assessments after approximately:

- 30 seconds
- One minute
- Five minutes
- Further significant on-chain events

## Risk Analysis

The platform would analyse:

- Creator-wallet history and original funding sources
- Connections between creators, early buyers and major holders
- Bundled or artificially distributed token supply
- Mint, freeze and other token authorities
- Liquidity ownership and potential withdrawal risk
- Suspicious buy-and-sell patterns
- Wash trading and artificial volume
- Buyer diversity versus transaction count
- Insider selling and wallet coordination
- Whether the token can be successfully sold
- Previous tokens associated with connected wallets

The output would be a clear risk score accompanied by specific explanations. Rather than only displaying **High Risk**, the platform might report:

> **High risk:** 14 of the largest holders were funded by the same wallet, 63% of early volume appears coordinated, and the creator is connected to three previous collapsed launches.

> [!IMPORTANT]
> All assessments would be probabilistic and presented as risk intelligence—not as guarantees or investment recommendations.

## What Makes It Different

The project should not position itself as another basic rug checker.

Its main differentiator would be **early behavioural prediction**. The system would examine how a market behaves during its opening minutes and identify patterns associated with previous scams.

Recent research covering **6.4 million Solana tokens** demonstrated that conventional machine-learning models could identify potential rug pulls using only the first five minutes of trading activity.[^2] A separate 2026 study identified organised fraud syndicates, wallet clusters and recurring liquidity-manipulation patterns across Solana.[^3]

This gives us a strong technical and research foundation for developing a product with measurable performance rather than relying on an unexplained AI-generated score.

## Human and Agent Products

The platform would have two connected products.

### Free Trader Platform

A public website and Telegram bot where users could:

- Search any Solana token
- View its live risk score
- Explore connected wallet clusters
- Receive alerts when its risk changes
- See the evidence behind each warning
- Track newly launched tokens through a live dashboard

This would provide visibility, build a community and generate the data needed to improve the system.

### Paid Agent and Trading API

Trading bots, wallets and autonomous agents could query a machine-readable endpoint before completing a swap.

```http
GET /risk/{token-address}
```

The API would return:

- An `allow`, `caution` or `deny` recommendation
- The underlying risk factors
- Model confidence
- Assessment timestamp
- Model version

Access could be sold through Solana's **x402 payment protocol** for a small USDC payment per assessment. Solana has recorded more than 37 million x402 transactions and recently introduced **Payment Channels**, allowing agents to make high volumes of paid API calls while settling them efficiently.[^4][^5]

This gives the project a direct revenue model and makes it relevant to both the Solana trading market and the emerging autonomous-agent economy.

## Proposed MVP

A credible first version could be developed without creating a complex custom smart contract.

The initial MVP would include:

1. Monitoring new Pump, Raydium and Meteora markets.
2. Static token and liquidity security checks.
3. Creator and early-holder wallet analysis.
4. Live transaction and liquidity monitoring.
5. An initial explainable risk-scoring model.
6. A basic public token-scanning dashboard.
7. Telegram risk alerts.
8. A paid x402 API endpoint for trading agents.
9. Cryptographically signed assessment results.

A focused MVP should be achievable in approximately **four to six weeks**, depending on data-provider access and the amount of historical processing required.

## Commercial Model

Potential revenue streams include:

- Pay-per-query API access in USDC
- Monthly plans for active traders
- Higher-volume packages for bots and trading platforms
- Wallet and DEX integrations
- White-label risk infrastructure
- Premium real-time alerts and wallet-cluster analysis

The core product should earn revenue independently of any project token.

## Token Strategy

A token should not be the first deliverable. Initially launching the working security product would give the project credibility, generate real usage and avoid appearing like another speculative token launch.

Once the platform has demonstrated demand, a token could potentially support:

- Staking by independent threat-intelligence contributors
- Rewards for correctly identifying malicious activity
- Penalties for manipulated or consistently inaccurate submissions
- API fee discounts
- Community governance over confirmed scam labels
- Access to advanced datasets or platform features

Any token should therefore be introduced only when it provides necessary utility to an already-functioning network.

## Why This Project Is Well Positioned

This concept combines several strong narratives without depending entirely on hype:

- Solana's high trading volume
- The continuing popularity of rapid token launches
- Increasing demand for fraud protection
- AI and machine-learning analysis
- Autonomous trading agents
- x402 machine-to-machine payments
- A genuine cybersecurity use case
- A scalable API-based business model

It is also considerably more achievable than building another DEX, launchpad or regulated real-world-asset platform.

## Proposed Next Step

The first stage should be a short technical-validation sprint. We would select a historical set of legitimate and fraudulent token launches, reconstruct their first five minutes of activity and test whether our proposed features can reliably distinguish between them.

If the results are promising, we can proceed with the live data pipeline, public dashboard and agent API.

> **Intended market position:** A real-time security and threat-intelligence layer for Solana traders, wallets and autonomous agents.

## References

[^1]: [Solana DEX Volume — DefiLlama](https://defillama.com/dexs/chain/solana)
[^2]: [Catching the Rug: Early Prediction of Fraudulent Memecoins on Solana via Machine Learning](https://arxiv.org/abs/2608.20271)
[^3]: [SolRugDetector: Investigating Rug Pulls on Solana](https://arxiv.org/abs/2603.24625)
[^4]: [x402 on Solana](https://solana.com/x402)
[^5]: [Payment Channels: 1 Million Payments Per Second — Solana](https://solana.com/news/payment-channels-1-million-payments-per-second)
