# ✨ So you want to sponsor a contest

This `README.md` contains a set of checklists for our contest collaboration.

Your contest will use two repos:

- **a _contest_ repo** (this one), which is used for scoping your contest and for providing information to contestants (wardens)
- **a _findings_ repo**, where issues are submitted.

Ultimately, when we launch the contest, this contest repo will be made public and will contain the smart contracts to be reviewed and all the information needed for contest participants. The findings repo will be made public after the contest is over and your team has mitigated the identified issues.

Some of the checklists in this doc are for **C4 (🐺)** and some of them are for **you as the contest sponsor (⭐️)**.

---

# Contest setup

## ⭐️ Sponsor: Provide contest details

Under "SPONSORS ADD INFO HERE" heading below, include the following:

- [ ] Name of each contract and:
  - [ ] lines of code in each
  - [ ] external contracts called in each
  - [ ] libraries used in each
- [ ] Describe any novel or unique curve logic or mathematical models implemented in the contracts
- [ ] Does the token conform to the ERC-20 standard? In what specific ways does it differ?
- [ ] Describe anything else that adds any special logic that makes your approach unique
- [ ] Identify any areas of specific concern in reviewing the code
- [ ] Add all of the code to this repo that you want reviewed
- [ ] Create a PR to this repo with the above changes.

---

# ⭐️ Sponsor: Provide marketing details

- [ ] Your logo (URL or add file to this repo - SVG or other vector format preferred)
- [ ] Your primary Twitter handle
- [ ] Any other Twitter handles we can/should tag in (e.g. organizers' personal accounts, etc.)
- [ ] Your Discord URI
- [ ] Your website
- [ ] Optional: Do you have any quirks, recurring themes, iconic tweets, community "secret handshake" stuff we could work in? How do your people recognize each other, for example?
- [ ] Optional: your logo in Discord emoji format

---

# Contest prep

## ⭐️ Sponsor: Contest prep

- [ ] Make sure your code is thoroughly commented using the [NatSpec format](https://docs.soliditylang.org/en/v0.5.10/natspec-format.html#natspec-format).
- [ ] Modify the bottom of this `README.md` file to describe how your code is supposed to work with links to any relevent documentation and any other criteria/details that the C4 Wardens should keep in mind when reviewing. ([Here's a well-constructed example.](https://github.com/code-423n4/2021-06-gro/blob/main/README.md))
- [ ] Please have final versions of contracts and documentation added/updated in this repo **no less than 8 hours prior to contest start time.**
- [ ] Ensure that you have access to the _findings_ repo where issues will be submitted.
- [ ] Promote the contest on Twitter (optional: tag in relevant protocols, etc.)
- [ ] Share it with your own communities (blog, Discord, Telegram, email newsletters, etc.)
- [ ] Optional: pre-record a high-level overview of your protocol (not just specific smart contract functions). This saves wardens a lot of time wading through documentation.
- [ ] Designate someone (or a team of people) to monitor DMs & questions in the C4 Discord (**#questions** channel) daily (Note: please _don't_ discuss issues submitted by wardens in an open channel, as this could give hints to other wardens.)
- [ ] Delete this checklist and all text above the line below when you're ready.

---

# Vader contest details

- $71,250 USDC main award pot
- $3,750 USDC gas optimization award pot
- Join [C4 Discord](https://discord.gg/code4rena) to register
- Submit findings [using the C4 form](https://code423n4.com/2021-11-vader-protocol-contest/submit)
- [Read our guidelines for more details](https://docs.code4rena.com/roles/wardens)
- Starts November 9, 2021 00:00 UTC
- Ends November 15, 2021 23:59 UTC

This repo will be made public before the start of the contest. (C4 delete this line when made public)

# Introduction

Vader is a new form of liquidity protocol that seeks to be self-serving. It uses its own liquidity and awareness of asset purchasing power to support the creation of a collateralized stablecoin. It also is capable of using liquidity units as collateral for synthetic assets, of which it will always have guaranteed redemption liquidity for. It has a fair and transparent incentive strategy to maximise the depth of liquidity pools and adoption of synthetic assets. It uses a liquidity-sensitive fee to ensure safe and sustainable creation of debt, which can increase the capital efficiency of the system.

## Key Features

The following are the key features of Vader Protocol:

1. Uses a collateralized stablecoin settlement asset
2. An ability to burn VADER to mint USDV
3. Impermanent Loss protection for Liquidity Providers in the pools
4. Continuous liquidity pool incentives
5. An ability to mint interest-bearing synthetic assets from pool liquidity
6. An ability to borrow debt against USDV, VADER or Synthetic Assets

## Contracts

```bash
├── dex
│   ├── math
│   │   └── VaderMath.sol
│   ├── pool
│   │   ├── BasePool.sol
│   │   ├── VaderPoolFactory.sol
│   │   └── VaderPool.sol
│   ├── queue
│   │   └── SwapQueue.sol
│   ├── router
│   │   └── VaderRouter.sol
│   └── utils
│       └── GasThrottle.sol
├── dex-v2
│   ├── pool
│   │   ├── BasePoolV2.sol
│   │   └── VaderPoolV2.sol
│   ├── router
│   │   └── VaderRouterV2.sol
│   ├── synths
│   │   ├── SynthFactory.sol
│   │   └── Synth.sol
│   └── wrapper
│       ├── LPToken.sol
│       └── LPWrapper.sol
├── external
│   ├── interfaces
│   │   ├── AggregatorV3Interface.sol
│   │   ├── IUniswapV2Callee.sol
│   │   ├── IUniswapV2ERC20.sol
│   │   ├── IUniswapV2Factory.sol
│   │   └── IUniswapV2Pair.sol
│   ├── libraries
│   │   ├── Babylonian.sol
│   │   ├── BitMath.sol
│   │   ├── FixedPoint.sol
│   │   ├── FullMath.sol
│   │   ├── Math.sol
│   │   ├── UniswapV2Library.sol
│   │   ├── UniswapV2OracleLibrary.sol
│   │   └── UQ112x112.sol
│   ├── UniswapV2ERC20.sol
│   └── UniswapV2Pair.sol
├── governance
│   ├── GovernorAlpha.sol
│   └── Timelock.sol
├── interfaces
│   ├── dex
│   │   ├── pool
│   │   │   ├── IBasePool.sol
│   │   │   ├── ISwapQueue.sol
│   │   │   ├── IVaderPoolFactory.sol
│   │   │   └── IVaderPool.sol
│   │   ├── queue
│   │   │   ├── IGasQueue.sol
│   │   │   └── ISwapQueue.sol
│   │   └── router
│   │       └── IVaderRouter.sol
│   ├── dex-v2
│   │   ├── pool
│   │   │   ├── IBasePoolV2.sol
│   │   │   ├── IVaderPoolFactoryV2.sol
│   │   │   └── IVaderPoolV2.sol
│   │   ├── router
│   │   │   └── IVaderRouterV2.sol
│   │   ├── synth
│   │   │   ├── ISynthFactory.sol
│   │   │   └── ISynth.sol
│   │   └── wrapper
│   │       ├── ILPToken.sol
│   │       └── ILPWrapper.sol
│   ├── external
│   │   └── chainlink
│   │       └── IAggregator.sol
│   ├── governance
│   │   └── ITimelock.sol
│   ├── reserve
│   │   └── IVaderReserve.sol
│   ├── shared
│   │   └── IERC20Extended.sol
│   ├── tokens
│   │   ├── converter
│   │   │   └── IConverter.sol
│   │   ├── IUSDV.sol
│   │   ├── IVader.sol
│   │   └── vesting
│   │       └── ILinearVesting.sol
│   └── x-vader
│       └── IXVader.sol
├── Migrations.sol
├── mocks
│   ├── MockAggregatorV3.sol
│   ├── MockConstants.sol
│   ├── MockGovernorAlpha.sol
│   ├── MockTarget.sol
│   ├── MockTimelock.sol
│   ├── MockToken.sol
│   ├── MockUniswapV2Factory.sol
│   ├── MockUniswapV2Library.sol
│   └── MockXVader.sol
├── reserve
│   └── VaderReserve.sol
├── shared
│   └── ProtocolConstants.sol
├── staking-rewards
│   ├── IStakingRewards.sol
│   ├── Owned.sol
│   ├── Pausable.sol
│   ├── RewardsDistributionRecipient.sol
│   └── StakingRewards.sol
├── tokens
│   ├── converter
│   │   └── Converter.sol
│   ├── USDV.sol
│   ├── Vader.sol
│   └── vesting
│       └── LinearVesting.sol
├── twap
│   └── TwapOracle.sol
└── x-vader
    └── XVader.sol
```

```
├── interfaces
│   ├── IERC20Metadata.sol
│   └── ITreasury.sol
├── lib
│   ├── FixedPoint.sol
│   └── FullMath.sol
├── Ownable.sol
├── test
│   └── TestToken.sol
├── Treasury.sol
└── VaderBond.sol
```

There are five different ERC20 tokens in the codebase. Two tokens Synth and LPToken under `dex-v2` directory are standard Burnable and Mintable ERC20 tokens. The LPToken represents liquidity issued in fungible tokens and its total supply is tracked by the Vader pool which represents total liquidity issued against the pair which is not necessarily equal to LPToken’s actual total supply as liquidity can be issued in non-fungible tokens as well.
The two tokens USDV and Vader under `tokens` directory are standard ERC20 tokens with Vader token having an emission curve covered over 5 years duration.
The token XVader under `x-vader` directory is a standard ERC20 token that inherits from `ERC20Votes` contract from Openzeppelin. This token is for governance purposes in Vader’s GovernorAlpha contract.

The Vader approach to implement pools of pairs is different from Uniswap’s. There is a singleton pool contract that implements the logic for pairs. All the pairs comprise of native and foreign assets. The native asset can be either USDV or Vader, while the foreign asset can be any ERC20 compatible token. The pool contract implements the logic for depositing and withdrawing of liquidity as well as swapping between the foreign assets among two different pairs and between native and foreign assets of a pair.
The liquidity issued against the pairs in pool can be in non-fungible token, fungible token or synthetic token.
There is a Vader Reserve contract that covers any impermanent loss experienced by liquidity providers.
The codebase implements a TWAP feature which makes use of aggregation over several Uniswap and Vader pools to determine the true USD value of Vader and USDV, respectively.
As xVADER token is mintable, the GovernorAlpha contract makes use of the snapshotted total supply of xVADER at the time of proposal creation to determine a proposal’s outcome.

VaderBond is a modification of Olympus DAO / Pro contracts

## Points of interest

Check if:

- The code under `dex-v2` directory should be reviewed for any exploits that allow draining of funds from the pool contract involving pairs.
- There is no inconsistency encountered in the liquidity issuance and redeeming as the liquidity is issued in non-fungible, fungible and synthetic tokens. They should work together seamlessly.
- The emission curve for Vader token works correctly by emitting the correct amount of tokens across eras.
- The TWAP contract properly and correctly calculates the true USD values for Vader and USDV assets, and the conversion between USDV and Vader is correct.
- The Veto functionality of GovernorAlpha contract works as intended and does not introduce any vulnerability.

- How should the Treasury.sol contract calculate value of principal token, same way as Olypmus DAO or Pro?
  Olympus DAO has two methods of calculation, one for RFV tokens and one for LP tokens.
  Olympus Pro has only one method of calculation.
- VaderBond removes FixedPoint library which is used in Olympus contracts. Will this cause rounding errors?
