---
layout: post
title: "Analysis of MAI Depegging Event"
date: 2023-07-23
categories: articles
---
Recently, the CDP stablecoin MAI experienced a depegging event, with its price falling to around 0.92 at one point and then recovering to 0.94 at the time of writing. This article provides a comprehensive analysis of the reasons behind MAI's depegging and its current situation. There have been articles like [medium:mai-stablecoin-july-2023-analysis](https://medium.com/@lain.iwakura44/mai-stablecoin-july-2023-analysis-e7978a40365) and [aave:chaos-labs-mai-depeg-update](https://web.archive.org/web/20231107172326/https://governance.aave.com/t/chaos-labs-mai-depeg-update/14108).

Let's start by grasping the balance sheet of MAI. The value of MAI is backed by repayment demand and the project's treasury, also known as Protocol Owned Liquidity. Therefore, the Equity of MAI can be calculated as the sum of the "good" Debt from MAI Vaults and the Protocol Owned Liquidity.

On the other hand, MAI's liability is represented by its nominal value, which corresponds to the number of tokens circulating in the market. In simple terms, Liability equals the total amount of MAI in circulation.

Since the multichain hack on July 6th, 2023, MAI's price has been under pressure from token liquidations fleeing from Fantom. These tokens lost their collateral value, causing the Debt on Fantom to turn into Bad Debt. As a result, MAI's Equity decreased. Additionally, with the Multichain bridge being closed, the circulating supply of MAI (Liability) also decreased. However, leaked MAI from Fantom accounted for only around 0.7 million, far from explaining the complete depegging situation. So, what caused the issue?

As a matter of fact, QiDAO had collaborated with several projects, allowing them to mint MAI outside the Vaults by accepting collateral. For instance, in [QIP027](https://snapshot.org/#/qidao.eth/proposal/QmSbkF4HGzaZ3zwNRiMQqsb12sqh1dk5FfBF23P1jNJVFZ), it was mentioned that 1 million of seed liquidity was provided. According to information from the Discord channel, MAI provided a total of 8 million in liquidity to market.xyz. However, when market.xyz was hacked, these MAI tokens became bad debt. QiDAO promised to gradually buy back these MAI using profits, transforming them into internal debt. Evidently, the progress of this conversion has been less than satisfactory.

Using publicly available information, we can estimate specific figures:

 - Based on data from [mai-lens](https://mai-lens.vercel.app/) and [QiDAO](https://app.mai.finance/analytics), "good debt" outside the Fantom chain amounts to $20.7 million.
 - According to [coingecko](https://web.archive.org/web/20231107172326/https://www.coingecko.com/en/coins/mai) and [dune](https://dune.com/guiling/mai-circulation), the circulating supply of MAI outside Fantom is 30.0 million.
 - Based on this [report](https://docs.google.com/spreadsheets/d/1npmvAIeBdDWa0_bCiFmhNtUTgCbW-sShIAVMnePb8O8/), Protocol Owned Liquidity (POL) amounts to $6.4 million, but note that 2.2 million is MAI. A reasonable approach is to consider this portion as "internal debt" and deduct it from both the circulating supply and POL. Additionally, POL includes $1.2 million in BIFI, which lacks liquidity. It is assumed that these BIFI tokens could be sold at half their market price through OTC trading. 

Thus, we get the final results:
 - Equity = 20.7m + 6.4m – 2.2m – 0.6m = 24.3m
 - Liability = 30.0m – 2.2m = 27.8m
 - Bad Debt = Liability – Equity = $3.5m
 - Fair value of MAI = Equity / Liability = 0.87

Keep in mind that these calculations involve estimates, as the potential POL on the Fantom chain and the value of POL were based on information from July 23rd and might not have been updated. In summary, these estimations are somewhat optimistic, and the actual situation is likely worse. Furthermore, since the MAI price is below $1, users who previously borrowed MAI are incentivized to repay it, leading to equal contractions in Equity and Debt, further deteriorating MAI's asset status. If the team tries to buy back MAI above its fair value, the effect is the same.

Originally, I posted this analysis in the QiDAO Discord group's investment talk channel. However, after I explained the official announcements to the members in the channel, I was removed from the group, and this analysis was deleted. As an enthusiast of Web3 and information freedom, I believe that people should have the right to access knowledge. Hence, I decided to publish this article. The writing is rushed, and many aspects are not elaborated upon, leaving them for readers to contemplate on their own.
