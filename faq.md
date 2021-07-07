# 常见问题

## **什么是mimo？**

mimo 是一款在 IoTeX 上具有自动化流动性的完全去中心化协议。mimo.exchange 是一个去中心化交易所（DEX），支持 IOTX 和 XRC20 等资产的点对点交易。 在 IoTeX 区块链的支持下，mimo 利用智能合约和自动做市 \(AMM\) 算法来管理流动性池并连接加密资产的买家/卖家。任何人都可以使用 mimo 为各种交易对进行交易和/或提供流动性，包括像 IOTX/ioBUSD 这样的跨链 IoTeX-Ethereum 交易对。

## 跨链交易是如何运作的？

mimo.exchange works with [ioTube](https://tube.iotex.io/), a decentralized cross-chain bridge between IoTeX and other blockchain networks, to support cross-chain trading. For any assets supported on ioTube, they can be added to mimo in no time. At current stage, all ERC20 assests that ioTube supports are tradable on mimo.



mimo.exchange 是与 [ioTube](https://tube.iotex.io/) 共同协作的，ioTube 是实现IoTeX 和其他区块链网络之间进行跨链交易的去中心化跨链桥梁。对于 ioTube 上任何支持的资产，它们都可以被立即添加至 mimo。当前，ioTube 支持的所有 ERC20 资产都可以在 mimo 上进行交易。

## **mimo的用户是？**

mimo用户主要分为三类：

**- 交易者：**买卖加密货币（通过“兑换”选项）

**- 流动性提供者：**资产存入智能合约以获得流动性挖矿奖励（通过“资金池”选项）

**- 开发人员：**将 mimo 连接到其他 dApp 或服务以进行即时兑换、借贷和其他 DeFi 用例。 [更多详情...](https://docs.mimo.finance/mimo-v1/api)

## 什么是去中心化交易所 \(DEX\)?

去中心化交易所 \(DEX\) 是一种加密货币交易所，无需中央授权即可运行。去中心化交易所允许加密货币进行点对点交易。由于用户不需要将他们的资产存入交易所，去中心化交易所降低了交易所被黑客窃取的风险。

## mimo 如何确保交易安全可信？

mimo 由一组可验证、不可篡改的智能合约提供支持，每个合约管理一个由 IOTX/XRC20 交易对构成储备金的“流动性池”。mimo.exchange 的智能合约基于Uniswap V1的智能合约，该合约已在实践中得到广泛使用和验证。mimo使用自动做市商 \(AMM\) 代替传统加密货币交易所使用的中心化方式，使用智能合约进行定价和储备金管理。交易者可以依据AMM智能合约保证的价格与这些储备金进行交易。

## 什么是自动做市商 \(AMM\)？

自动做市商 \(AMM\) 是一种利用算法管理流动性池的方法。使用 AMM，无需使用订单簿或等待订单履行。再加上 IoTeX 独特的 5 秒确定性，使得交易可以非常快地完成。[更多详情...](https://docs.mimo.exchange/the-formulas)

## **如何进行交易？**

For step-by-step trading instructions, please refer to the [mimo user guide](https://community.iotex.io/t/mimo-trading-on-mimo-step-by-step-instructions/1524).  
要访问 mimo，首先需要一个 IoTeX 地址——这可以通过 IoTeX 的官方钱包 ioPay 创建。在ioPay中打开mimo并连接到钱包。你需要在交易前准备一些 IOTX 来支付 gas 费用——值得一提的是，mimo 的费用非常低，几乎为零！ 在“兑换”选项中，你可以浏览各种交易对的汇率并通过 ioPay 钱包签名来进行交易。

有关分步交易的说明，请参阅 [mimo 用户指南](https://community.iotex.io/t/mimo-trading-on-mimo-step-by-step-instructions/1524)。

## 我该如何使用流动性池？

流动性提供者是将 IOTX 和 XRC20 代币组成交易对，存入流动性池中以换取池代币的人。这些池代币代表着流动性提供者对该池的资产以及池中所有交易费用具有部分所有权，并且流动性提供者可以随时赎回其存入资产。根据存入资产价格的变化，对应的池代币的价值也会波动——因此，流动性提供者在承担价格风险的同时，还会获得费用补偿。

有关提供流动性的相关说明，请参阅 [mimo 用户指南](https://community.iotex.io/t/mimo-managing-liquidity-pools-step-by-step-instructions/1523)。

## 交易费用是多少？

所有交易费用仅为源代币的 0.3%。所有的交易费用将进入流动性池，供所有流动性提供者使用。

## mimo中所有代币都是可信的吗?

**牢记：不要相信，永远质疑！**

mimo 是一款开放性的协议，允许在未经许可的情况下交易任何代币。任何人都可以在 IoTeX 上创建任何名称的 XRC20 代币，当然，这有可能会出现虚假代币。 

如果您通过代币地址与任意代币进行兑换，或标记为“自行上市”，请格外小心并在交易前对代币的可信度进行研究。

您购买的任何代币都存在无法将其赎回的可能。

最佳做法是：

1. 你可以放心地交易mimo中默认列表里的代币，不包括“自行上市”的代币。
2. 当你对以下类型的代币进行交易时

   1. 自行上市的代币
   2. 你使用代币地址添加的代币
   3. 通过外部网站特定的URL添加的代币

   请仔细检查代币地址，并研究它是否是您想要交易的代币。你可以这么做：

   1. 研究代币的发行网站并试着在网站上找到代币地址
   2. 在社交渠道寻求帮助，例如： [http://t.me/mimochat](http://t.me/mimochat)
   3. 始终质疑代币甚至项目是否具备合法性

## 如何在mimo上线我的代币？

如果你目前开展的项目刚好拥有项目代币，那么恭喜，mimo 是一个允许你的用户交易你的代币的好平台！将代币在mimo上线，只需要为你的代币添加流动性即可。第一次增加流动性需要创建一个“交易”合约， 此后任何人都可以为你的代币增加流动性。

一旦您的代币添加了流动性，它就会显示在 mimo 分析中 \([info.mimo.exchange](https://info.mimo.exchange/)\)。 一旦流动性价值超过200K IOTX，mimo.exchange界面中，代币会显示为“Self Listed”。

你可以将你的代币提交至 IoTeX 的代币数据库中，将代币的logo和代币数据信息添加到 iotexscan。 mimo 将跟踪来自 iotexscan 上所有代币的数据。

如何在 IoTeX 网络上发行代币，请参考：  
 [https://docs.iotex.io/developer/smart-contracts/issue-tokens.html](https://docs.iotex.io/developer/smart-contracts/issue-tokens.html)

