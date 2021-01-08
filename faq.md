# FAQ

## **What is mimo?**

mimo is a decentralized protocol with automated liquidity on IoTeX blockchain. mimo.exchange is a decentalized exchange \(DEX\) that enables peer-to-peer trading of IOTX and XRC20 assets. Powered by the IoTeX blockchain, mimo utilizes smart contracts and automated market making \(AMM\) algorithms to manage liquidity pools and connect buyers/sellers of crypto assets. Anyone can use mimo to trade and/or provide liquidity for a variety of trading pairs, including cross-chain IoTeX-Ethereum pairs like IOTX/ioBUSD.

## How does cross-chain trading work?

mimo.exchange works with [ioTube](https://tube.iotex.io/), a decentralized cross-chain bridge between IoTeX and other blockchain networks, to support cross-chain trading. For any assets supported on ioTube, they can be added to mimo in no time. At current stage, all ERC20 assests that ioTube supports are tradable on mimo.

## **Who can use mimo?**

There are three main categories of mimo users:

**- Traders:** buy and sell cryptocurrencies \(via the “Swap” tab\) 

**- Liquidity Provider:** deposit assets into smart contracts to earn liquidity mining rewards \(via the “Pool” tab\) 

**- Developers:** connect mimo to other dApps or services for instant swaps, lend/borrow, and other DeFi use cases. [Learn More](https://docs.mimo.exchange/api)

## What is a decentralized exchange \(DEX\)?

A decentralized exchange \(DEX\) is a cryptocurrency exchange which operates without a central authority. Decentralized exchanges allow peer-to-peer trading of cryptocurrencies. Because users do not need to deposit their assets to the exchange, decentralized exchanges reduce the risk of theft from hacking of exchanges.  


## How does mimo ensure trusted trades?

mimo is powered by a set of verifiable, non-upgradeable smart contracts, which each manage a “liquidity pool” made up of on-chain reserves of IOTX/XRC20 tokens. mimo.exchange's smart contract is based on Uniswap's V1 contract, which has been widely used and tested in practise. Instead of a centralized order book used by traditional cryptocurrency exchanges, mimo utilizes an automated market maker \(AMM\) smart contract for pricing and reserve management. Traders can trade against these reserves at prices guaranteed by the AMM smart contract.

## What is Automated Market Making \(AMM\)?

Automated Market Making \(AMM\) is a way of managing a liquidity pool using algorithm. With AMM, no orderbook or waiting for order fulfillment is needed. Together with IoTeX's 5 second finality, the trades can be very lightning fast. [Learn More](https://docs.mimo.exchange/the-formulas)

## **How do I trade?**

To access mimo, you must first have an IoTeX address. You can create via ioPay, the official IoTeX wallet for Desktop and Mobile. With your ioPay open, open mimo App \(coming\) and connect your wallet. Before trading, you will need some IOTX for gas fees – luckily, mimo’s fees are very low, almost-zero! Under the “Swap” tab, you can now browse the swap rates of various trading pairs and execute trades by signing with your ioPay wallet. 

For step-by-step trading instructions, please refer to the [mimo user guide](https://community.iotex.io/t/mimo-trading-on-mimo-step-by-step-instructions/1524).

## How do I participate in liquidity pools?

A liquidity provider is someone who deposits IOTX and XRC20 tokens into the pair’s liquidity pool reserves in return for pool tokens. These pool tokens represent fractional ownership of the total pool reserves, which also include all transaction fees, and can be redeemed for the underlying deposited assets at any time. Based on the price movements of the deposited assets, the value of one’s pool tokens will fluctuate – as such, liquidity providers take on price risk and are compensated with fees. 

For instructions on providing liquidity, please refer to the[ mimo user guide](https://community.iotex.io/t/mimo-managing-liquidity-pools-step-by-step-instructions/1523).

## What is the trading fees?

All trading fees are just 0.3% of source token. The fees will 100% go to liquidity pool for share among all liquidity providers.

## Do I trust tokens on mimo?

In short, don't trust, always question! 

mimo is an open protocol that allows trading of any tokens without permission. Anyone can create XRC20 token on IoTeX with any name, including fake tokens. 

If you are interacting with an arbitrary token by its token address, or labeled as "Self listed", please take extra caution and do your research before trading.

If you purchase an arbitrary token, you may be unable to sell it back.

The best practice are

1. you can safely trade tokens on mimo's list, excluding "Self listed" ones.
2. when you trade one of the following types of tokens 

   1. Self listed
   2. added by you using token address
   3. added by a particular URL from external websites

   Please double check the token address and research if it is your desired token to trade. Things you can do are 

   1. Research the token's issuers website and try to find a token address on the website
   2. Ask for help in social channels like: [http://t.me/mimochat](http://t.me/mimochat)
   3. Always question if the tokens or even projects are legit.

## How do I list my token on mimo?

If you are working on a project with a token, congrats, mimo is a great place to allow your users to trade your tokens. To list on mimo, you can simply add liquidity to your token. The first time of adding liquidity will have a process of creating an "exchange" contract. Thereafter, anyone can add liquidity.

Once your token is added with some liquidity, it would show up in mimo analytics \(info.mimo.exchange\). Once the liquidity surpasses 200K IOTX, it would show up in mimo.exchange interface as "Self Listed".  

You can submit your token to IoTeX's token metadata github repository to add logo and metadata to iotexscan. mimo will follow the data from iotexscan.

You can refer to [https://docs.iotex.io/developer/smart-contracts/issue-tokens.html](https://docs.iotex.io/developer/smart-contracts/issue-tokens.html) for how to issue a token on IoTeX network.

