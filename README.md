# Reservoir
#### A [HackMoney 2022](https://hack.ethglobal.com/hackmoney2022/) Project
For full context please [read the user story](https://hackmd.io/@kitblake/BkkYw1bwc) that explains the use case.

## Streaming Money Reservoirs – Technical Description

The primary component is a Dapp called a Reservoir. It acts as a DeFi Vault and manages supply to DeFi protocols. It also allows [Superfluid](https://superfluid.finance/) money streams to flow in or out. A Reservoir is locked and only accessible via its creator wallet. 

- A Reservoir is created by deploying the contract from a template.
- The wallet that creates the Reservoir can access the contract via a frontend.
  - (This is similar to Zapper, Zerion, and other finance management Dapps.)
- Config and parameters of the Reservoir can be modifed by the owner.
- The UI is a dashboard which shows all activity managed by the Reservoir.
  - It displays balances, incoming and outgoing streams, and DeFi supplies and rewards.
  - The connected DeFi protocols have parameters that can be adjusted.
  - The streams can be modified like any Superfluid stream.
- A proportion of the currency reserves can be supplied to DeFi protocols like Aave, Compound, Curve, etc.
- The allocations are managed automatically based on settings in the dashboard.

### Creation
The steps to create a functioning Reservoir are:
- Visit the app site and deploy a Reservoir contract using an Ethereum wallet.
- Fund the Reservoir with currency.
- Setup streams for payments:
  - Each Superfluid stream must deposit a buffer bond, based on the flow rate.
  - These streams determine the minimum currency reserves required in the Vault.
  - Once flowing, the streams can be edited, e.g. reduced during low activity.
- When the outgoing streams are set up the remaining balance can be invested:
  - Choose desired DeFi protocols (Aave, Compound, Yearn, etc).
  - Configure parameters such as proportion of balance to be invested.
  - Make initial supply deposits.
  - Configure withdrawal parameters to keep the outgoing streams funded:
    - Withdrawals are triggered based on reserve balance proportions.
    - Depending on the currencies used some streams might need SuperToken swaps.
- If the Reservoir has incoming streams the steps are similar but with deposits.
  - Configure parameters (frequency, proportions) for new DeFI supplies.
