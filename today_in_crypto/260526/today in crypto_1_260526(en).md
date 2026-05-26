---
date: 2026-05-26
lang: en
---

Today we are focusing on a few stories from the DeFi ecosystem, where there never seems to be a quiet day. Sometimes it feels difficult, sometimes oddly flimsy, and it still seems like the future. Then again, sometimes you look at it and think, "Decentralized? Really?"

# Module Hacks and AI Payments

On Ethereum and Base, a third-party Safe module named "SquidRouterModule" appears to have been exploited, draining about $3.2 million. Squid drew a clear line around the incident, saying it did not create or deploy the module, and that the module merely shared the SquidRouterModule name while being different from the core Squid Router contract. Fair enough. The important point is less about Safe itself and more about the fact that an external module approved by a wallet can effectively act like an agent for the vault. That is where this kind of exploit can appear.

The key question in this Safe-related incident is not simply, "Was the wallet itself hacked?" It is, "How much authority did the external module attached to the wallet actually have?" Safe is widely used as a multisig wallet, where multiple people must sign before assets can move. DAOs and project treasuries often rely on it. But if you attach an external module to Safe, certain tasks can be automated. For example, it might send a fixed amount of operating expenses to someone every month. Getting three multisig signers to approve that every single time can be slow and inefficient. So a team can attach a module to Safe and say, in effect, "This module is an approved program. If it makes a request within the rules we set, let it move Safe funds without getting three signatures every time, alright?"

It feels like a world where AI handles payments is coming pretty soon, does it not? Coinbase introduced x402 in May last year. It is a payment protocol that lets AI agents or apps pay for APIs, services, and content with stablecoins inside the normal flow of HTTP requests. Since then, it has led to the x402 Foundation with Cloudflare, a move under the Linux Foundation, and the AWS Bedrock AgentCore Payments preview. At this point, it is becoming one of the early standard candidates for an internet where AI agents spend money. You can also imagine a world where the hacked module from the first story is replaced by an AI agent. How much authority should we give it? How should we prepare for all the strange situations that follow? We will have to keep watching. Exciting times, I suppose.

+ Safe module exploit report: https://www.theblock.co/post/402487/we-dont-know-who-deployed-this-squid-distances-itself-from-3-2-million-third-party-module-exploit
+ Cointelegraph's Safe and Squid summary: https://cointelegraph.com/news/squid-safe-labs-third-party-module-3-2-million-exploit
+ Safe official docs - what modules are: https://docs.safe.global/advanced/smart-account-modules
+ Coinbase's first x402 introduction: https://www.coinbase.com/en-it/developer-platform/discover/launches/x402
+ Cloudflare and Coinbase announce the x402 Foundation: https://blog.cloudflare.com/x402
+ AWS Bedrock AgentCore Payments preview: https://aws.amazon.com/about-aws/whats-new/2026/04/amazon-bedrock-agentcore-payments-preview/
+ Coinbase announcement that x402 added Polygon support: https://www.coinbase.com/developer-platform/discover/launches/x402facilitator-polygon

# Some Things Are Not Module Failures

So does that mean the wallet itself is completely safe? Not quite. According to The Block, EURR and USDR from European stablecoin issuer StablR depegged. "Depegged" can sound like a difficult word, but it simply means the euro stablecoin could no longer maintain a price of 1 euro, and the dollar stablecoin could no longer maintain a price of 1 dollar. In short, they failed to live up to their own names.

It appears that StablR's minting authority was shared by three people. Think of it like a company credit card. A company does not usually have just one corporate card. People in roles that require company spending have company cards. This seems a bit like someone outside the company stealing one of those cards and using it wildly. The setup was reportedly a 1-of-3 multisig. Three people had signing authority, and a transaction could go through if just one of them signed. That wallet also had the ability to issue stablecoins. The attacker obtained one of those private keys, added themselves as an administrator, and replaced the existing owners. Then they minted new stablecoins and swapped them for Ethereum on decentralized exchanges. Because the market suddenly had more stablecoins being dumped than there was demand to buy them, the price of the stablecoins fell. You could also understand it as not robbing the bank vault, but stealing the minting authority, printing new money, and throwing it into the market.

Security firm Blockaid viewed the incident not as a smart contract bug, but as a failure of key management and governance. If you are tempted to dismiss StablR as some lightweight operation, that would be too easy. It has reportedly received strategic investments from well-known industry names such as Tether and Kraken. It has also been introduced with words like European regulation, MiCA, reserves, and transparency. So how should we interpret this? Should we think, "Wow, the crypto industry is a total mess?" Or should we think, "So much for decentralization, huh?"

There is clearly a lot of homework left. I like the Korean crypto thinker and writer Oh Tae-min. He recently published a new book, and in the preface to *There Is No Future Without Ethereum*, he writes:

> Ethereum did not survive because it was perfect. It survived because it had a structure that could withstand failure. As a result, Ethereum became more than a simple blockchain platform. It became a new continent where new financial experiments take place.
> *There Is No Future Without Ethereum*, p. 9

Exactly. Maybe all of these incidents become fertilizer in the end. Anyway, this ever-restless DeFi ecosystem is something I plan to keep following closely. Something is definitely being built here. Probably.

+ The Block's report on StablR EURR and USDR depegging: https://www.theblock.co/amp/post/402429/stablrs-eurr-and-usdr-depeg-after-attacker-mints-13-5-million-in-unbacked-tokens-through-multisig-exploit
+ CoinDesk follow-up on StablR freezing tokens: https://www.coindesk.com/markets/2026/05/26/stablr-freezes-usdr-and-eurr-after-attacker-mints-usd13-5-million-in-unbacked-tokens
+ StablR official proof-of-reserve page: https://www.stablr.com/proof-of-reserve
+ StablR official homepage - EURR and USDR introduction: https://www.stablr.com/
+ StablR USDR official docs: https://docs.stablr.com/docs/what-is-eurr-copy
