# Open Payroll

- **Team Name:** PolkaLadris
  > > TODO
- **Payment Address:** BTC, Ethereum (USDT/USDC/DAI) or Polkadot/Kusama (aUSD) payment address. Please also specify the currency. (e.g. 0x8920... (DAI))
- **[Level](https://github.com/w3f/Grants-Program/tree/master#level_slider-levels):** 1, 2 or 3

## Project Overview :page_facing_up:

Open payroll aims to cover the needs of an organization that wants to pay transparently over each certain period of time. Everyone can see the address of each of the participants in the smart contract and a multiplier that's being applied. This concept could be related to a salary and the seniority of the receiver, schedule regular payments or subscriptions, or any other example where regular payment could be applied.

There would be a factory contract with an interface to be able to configure the payroll contract. The payroll contract will be owned by the creator. This creator could be a DAO address, a multisig or a single person. The contract will manage a treasury from where all the payments will be discounted. There should be a base amount, and a multiplier to each account and given a period of time each account can claim the payment to the contract.

This first version we will manage a stable coin currency, but we aim to use the treasury asset as something that can be changed by the owner.

### Overview

- Transparent payment from a treasury contract.
- The project aims to cover a perodical payment of an organization to members/employees/providers/agents and this will be done automatically.
- All the Polkadot ecosystem and people from outside can use this project to solve the payroll issue in a transparent way.
- The team wanted to create this project in order to apply the knowledge we got from PBA Buenos Aires 2023 in a real project that can solve a problem for the people in the real life.

### Project Details

>> TODO
- Mockups/designs of any UI components

In the payroll contract there will be different entities and the interface will be some messages most of the self explicit:

    - Payees
      - Add Payee
      - Remove Payee
      - Update Payee
      - Get Payee

    - Payroll
      - Pause Payroll -> just in case there will need to pause
      - Resume Payroll
      - Get Payroll Status (is paused or not)
      - Get Treasury Balance 
      - Get Next Payroll Amount -> calculate the total amount it has to pay on the next period
      - Get Payroll Period Duration -> in blocks

    - Payroll Config (most of this parameters are set on the constructor but they can be changed by the owner)
      - Set Base Payment
      - Set Payroll Period Duration
      - Set Payroll Start Date
      - Set Payroll End Date

    - Payroll Actions
      - Claim Payroll (payee)
      - Transfer Treasury (owner) // we thought about this functionallity in order to be able to migrate the contract to future versions.

For interacting with the contract we will provide a web interface with a config file to set the blockchain where the Factory contract is deployed. The interface will provide the fields to fill in order to create a new payroll contract. Set a name, set base payment, set duration and establish the start date. 
After that you will be lead to the add Payee screen in order to add payees to the new brand contract.

In the contract will be stored only the address where the payment will be sent. In the ui, you'll be able to identify each address by adding a name and an email for notifications. All the metadata information will be stored in the browser's local storage. 

After that you'll be presented with an interface to choose which payroll contract you want to interact with. That's why is important to set a proper name in the first interaction. Since that name it won't be on chain there will be an option to edit it.

When you enter the contract page you'll be able to edit it's name, see all payees, call addPayee, removePayee, updatePayee functions, get balances, pause and resume, check amounts for next iteration (very usefull if you want to check you'll be able to pay next period).

There will be also the claim payroll screen where each payee can connect it's wallet and claim the payment for that period, or the accumulated amount in case they have more than one period to redeem.

The Transfer Treasury  function won't be showed. That function was thought in case you want to migrate the treasury founds to a newer version.

Just in case you want to change computer or clean your local storage there will be an option to store locally your contracts metadata. There will be corresponding restore from a file previously downloaded.

- Data models / API specifications of the core functionality
- An overview of the technology stack to be used
- Documentation of core components, protocols, architecture, etc. to be deployed
- PoC/MVP or other relevant prior work or research on the topic
- What your project is _not_ or will _not_ provide or implement
  - This is a place for you to manage expectations and to clarify any limitations that might not be obvious

Things that shouldn’t be part of the application (see also our [FAQ](../docs/faq.md)):

- The (future) tokenomics of your project
- For non-infrastructure projects—deployment and hosting costs, maintenance or audits
- Business-oriented activities (marketing, business planning), events or outreach

### Ecosystem Fit

Help us locate your project in the Polkadot/Substrate/Kusama landscape and what problems it tries to solve by answering each of these questions:

- Where and how does your project fit into the ecosystem?
- Who is your target audience (parachain/dapp/wallet/UI developers, designers, your own user base, some dapp's userbase, yourself)?
- What need(s) does your project meet?
- Are there any other projects similar to yours in the Substrate / Polkadot / Kusama ecosystem?
  - If so, how is your project different?
  - If not, are there similar projects in related ecosystems?

## Team :busts_in_silhouette:

### Team members

- Luca Auet
- Ezequiel Golub
- Gabriel González
- Tomas Rawski

### Contact

- **Contact Name:** Gabriel González
- **Contact Email:** gabrielnicolasgonzalez@gmail.com

### Legal Structure

We don't have a legal structure. We are a group of developers that want to build together. Probably we will create a legal structure for future projects.

### Team's experience

We know each other from different places but we began working together at the Polkadot Blockchain Academy 2022 in Buenos Aires, Argentina.

Here are some brief backgrounds on each of us:

- Ezequiel has experience as a CTO of a learning platforms with more that 100K users. He has worked as backend Developor in Rappi.
- Gabriel, Luca and Tomas are advocates from The Graph Protocol. They have experience building subgraphs for different projects including CowSwap, MakerDAO and Lens protocol.
- At the Latam Hackathon of Polkadot (https://polkadothackathonlatam.com), Gabriel and Luca won first place in the Web3/Blockchain Tooling category with their project (https://polkadothackathonlatam.com/proyecto-inner/LactobaciloGG/usuario-single/).
- Tomas is a full-stack and Solidity developer with several years of experience.

### Team Code Repos

- https://github.com/protofire/messari-subgraphs
- https://github.com/0xLucca/Dakers
- https://github.com/0xLucca/pba-assignment-2-frontend
- https://github.com/protofire/maker-protocol-subgraph
- https://github.com/rtomas/OracleSolver-ChainLink
- https://github.com/rtomas/lens-protocol-subgraph
- https://github.com/cowprotocol/subgraph
- https://github.com/alongoni/polkadot-contract-wizard
- https://github.com/Altoros/swarm-markets-subgraph

Please also provide the GitHub accounts of all team members. If they contain no activity, references to projects hosted elsewhere or live are also fine.

- https://github.com/0xLucca
- https://github.com/ezegolub
- https://github.com/GabrielCamba/
- https://github.com/rtomas

### Team LinkedIn Profiles (if available)

- https://www.linkedin.com/in/lucaauet/
- https://www.linkedin.com/in/ezegolub/
- https://www.linkedin.com/in/gabriel-nicolas-gonzalez/
- https://www.linkedin.com/in/tomas.rawski

## Development Status :open_book:

If you've already started implementing your project or it is part of a larger repository, please provide a link and a description of the code here. In any case, please provide some documentation on the research and other work you have conducted before applying. This could be:

- links to improvement proposals or [RFPs](https://github.com/w3f/Grants-Program/tree/master/docs/RFPs) (requests for proposal),
- academic publications relevant to the problem,
- links to your research diary, blog posts, articles, forum discussions or open GitHub issues,
- references to conversations you might have had related to this project with anyone from the Web3 Foundation,
- previous interface iterations, such as mock-ups and wireframes.

## Development Roadmap :nut_and_bolt:

This section should break the development roadmap down into milestones and deliverables. To assist you in defining it, we have created a document with examples for some grant categories [here](../docs/Support%20Docs/grant_guidelines_per_category.md). Since these will be part of the agreement, it helps to describe _the functionality we should expect in as much detail as possible_, plus how we can verify and test that functionality. Whenever milestones are delivered, we refer to this document to ensure that everything has been delivered as expected.

Below we provide an **example roadmap**. In the descriptions, it should be clear how your project is related to Substrate, Kusama or Polkadot. We _recommend_ that teams structure their roadmap as 1 milestone ≈ 1 month.

> :exclamation: If any of your deliverables is based on somebody else's work, make sure you work and publish _under the terms of the license_ of the respective project and that you **highlight this fact in your milestone documentation** and in the source code if applicable! **Teams that submit others' work without attributing it will be immediately terminated.**

### Overview

- **Total Estimated Duration:** Duration of the whole project (e.g. 2 months)
- **Full-Time Equivalent (FTE):** Average number of full-time employees working on the project throughout its duration (see [Wikipedia](https://en.wikipedia.org/wiki/Full-time_equivalent), e.g. 2 FTE)
- **Total Costs:** Requested amount in USD for the whole project (e.g. 12,000 USD). Note that the acceptance criteria and additional benefits vary depending on the [level](../README.md#level_slider-levels) of funding requested. This and the costs for each milestone need to be provided in USD; if the grant is paid out in Bitcoin, the amount will be calculated according to the exchange rate at the time of payment.

### Milestone 1 Example — Basic functionality

- **Estimated duration:** 1 month
- **FTE:** 1,5
- **Costs:** 8,000 USD

> :exclamation: **The default deliverables 0a-0d below are mandatory for all milestones**, and deliverable 0e at least for the last one.

|  Number | Deliverable               | Specification                                                                                                                                                                                                                                 |
| ------: | ------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **0a.** | License                   | Apache 2.0 / GPLv3 / MIT / Unlicense                                                                                                                                                                                                          |
| **0b.** | Documentation             | We will provide both **inline documentation** of the code and a basic **tutorial** that explains how a user can (for example) spin up one of our Substrate nodes and send test transactions, which will show how the new functionality works. |
| **0c.** | Testing and Testing Guide | Core functions will be fully covered by comprehensive unit tests to ensure functionality and robustness. In the guide, we will describe how to run these tests.                                                                               |
| **0d.** | Docker                    | We will provide a Dockerfile(s) that can be used to test all the functionality delivered with this milestone.                                                                                                                                 |
|     0e. | Article                   | We will publish an **article**/workshop that explains [...] (what was done/achieved as part of the grant). (Content, language and medium should reflect your target audience described above.)                                                |
|      1. | Substrate module: X       | We will create a Substrate module that will... (Please list the functionality that will be implemented for the first milestone. You can refer to details provided in previous sections.)                                                      |
|      2. | Substrate module: Y       | The Y Substrate module will...                                                                                                                                                                                                                |
|      3. | Substrate module: Z       | The Z Substrate module will...                                                                                                                                                                                                                |
|      4. | Substrate chain           | Modules X, Y & Z of our custom chain will interact in such a way... (Please describe the deliverable here as detailed as possible)                                                                                                            |
|      5. | Library: ABC              | We will deliver a JS library that will implement the functionality described under "ABC Library"                                                                                                                                              |
|      6. | Smart contracts: ...      | We will deliver a set of ink! smart contracts that will...                                                                                                                                                                                    |

### Milestone 2 Example — Additional features

- **Estimated Duration:** 1 month
- **FTE:** 1,5
- **Costs:** 8,000 USD

...

## Future Plans

Please include here

- how you intend to use, enhance, promote and support your project in the short term, and
- the team's long-term plans and intentions in relation to it.

## Referral Program (optional) :moneybag:

You can find more information about the program [here](../README.md#moneybag-referral-program).

- **Referrer:** Name of the Polkadot Ambassador or GitHub account of the Web3 Foundation grantee
- **Payment Address:** BTC, Ethereum (USDT/USDC/DAI) or Polkadot/Kusama (aUSD) payment address. Please also specify the currency. (e.g. 0x8920... (DAI))

## Additional Information :heavy_plus_sign:

**How did you hear about the Grants Program?** Web3 Foundation Website / Medium / Twitter / Element / Announcement by another team / personal recommendation / etc.

Here you can also add any additional information that you think is relevant to this application but isn't part of it already, such as:

- Work you have already done.
- If there are any other teams who have already contributed (financially) to the project.
- Previous grants you may have applied for.
