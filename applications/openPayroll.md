# Open Payroll

- **Team Name:** Polkadrys Labs
- **Payment Address:** BTC, Ethereum (USDT/USDC/DAI) or Polkadot/Kusama (aUSD) payment address. Please also specify the currency. (e.g. 0x8920... (DAI))
  TODO Complete the wallet
- **[Level](https://github.com/w3f/Grants-Program/tree/master#level_slider-levels):** 2

## Project Overview :page_facing_up:

Blockchain decentralized nature, transparency, and immutability make it a promising solution for many industries. We believe that blockchain technology has the potential to revolutionize the way we live our lives, and we want to be a part of that revolution.

At our core, we are a team of innovators who are passionate about leveraging blockchain technology to build real-life solutions. We believe that the power of blockchain can be harnessed to create a more transparent and secure world. Our goal is to create solutions that are not only technologically advanced, but also practical and applicable to everyday life.

We ran into a common problem while working for a crypto development shop: The payment process sometimes became erratic, partial payments, late payments and no transparency into how the final number that was assigned in a spreadsheet actually came to be. We believe that the blockchain can make this transparent to the members of a collective, without having to sacrifice privacy nor making it super cumbersome to use.

In recent years, a growing number of organizations have made a commitment to financial transparency, recognizing the benefits of sharing information about earnings with their employees and stakeholders. Tech workers' cooperatives in the Argentine Federation of Cooperatives [FACTTIC](https://facttic.org.ar/) are a notable example of this trend, providing detailed financial information to members.

In addition to cooperatives, several companies have positioned themselves as "open numbers" enterprises, providing employees with access to information about the salaries of both workers and owners [Ten Pines](https://cultura.10pines.com/#numeros-abiertos) is a good example of this trending culture. [Buffer](https://buffer.com/resources/revenue-dashboard/), for instance, publishes the salaries of all its employees on its website, and [Whole Foods](https://www.tableau.com/solutions/customer/whole-foods-market-democratizes-data-across-460-retail-stores-with-tableau) allows employees to access financial information on a need-to-know basis. These efforts reflect a growing recognition of the importance of financial transparency in promoting trust and accountability within organizations.

The benefits of financial transparency are not limited to the private sector, however. Nonprofit organizations such as Charity: Water and The Wikimedia Foundation have also made transparency a priority, regularly publishing detailed financial reports and making them available to the public. As transparency becomes more widespread, it is likely to become an increasingly important tool for promoting fairness, equity, and accountability across a range of sectors and organizations.

### Overview

The objective of Open Payroll is to meet the needs of organizations that wish to make transparent payments during a given period.
We will create a contract that enables anyone to configure and generate their own payroll system.

The payroll contract will be owned entirely by its creator. This creator could be a DAO address, a multisig or a single person. The contract will manage a treasury from where all the payments will be deducted. There will be a base amount and a set of multipliers associated to the addresses of the payees.

E.g. We create a payroll contract for paying developers salaries. We will have a base amount and only one multiplier which is the employee's seniority.
Alice is a junior employee and Bob is a senior employee. Alice's multiplier is 1 and Bob's multiplier is 2. The base amount is 1000. The payroll contract will allow Alice to claim 1000 and Bob 2000 every period.

The payroll smart contract transparently displays the addresses of all participants, along with the multipliers being utilized, allowing complete visibility to everyone. The initial rollout of this project will be super opinionated and geared towards an open payroll system, but this notion can later be applied to various scenarios, such as salaries, recurring payments, subscriptions, etc.

### Project Details

Based on what we exposed in the project Overview section and our past experience, we decided to implement a tool to takle this use case of the blockchain technology stack.

We plan to use the following tech stack in the latest stable version: React, Next.js, MUI, PolkadotJS wallet extension, Ink!, Rust, Docker, Git.

These are the steps that will be done to implement the proposed solution:

#### <a name="step1"></a>1.- Design a front end based on the wireframe proposed

This is the wireframe that we propose for the frontend:
//TODO El link a repo de github con las imagenes del wireframe

The development needs to be focused on making a good user experience, taking into account the user personas that will be using the product.

In this step we will create the mockup in Figma.

#### User Personas

- An owner or many owners of a company that want to open the numbers in order to be transparent in the way they manage payments in the organization.

- A cooperative that want to keep an automated payment of the payroll.

- A group managing the treasury, aiming to maintain regular payments while focusing on its growth.

#### <a name="step2"></a>2.- Develop the user interface based on the design created in the previous step.

Implement the frontend taking into account the usability guidelines created for being as easiest as it could be, in order to be usable by tech and non tech people.
The frontend will included a dashboard for the owner of the contract, where he will be able to create a new contract and configure its parameters. The frontend will also include a dashboard for the payees of the contract, where they will be able to claim the payments that are already released.

#### <a name="step3"></a>3.- Implement and test the payroll contract

We will develop a contract, which purpose is to manage a treasury, that will be spent by the parameters set by the owner at creation point. Those parameters can be changed over the time and more beneficiaries can be added or removed. The data contained on chain will be the addresses of the beneficiaries, the owners address, the period, the base payment and the multipiers. This information will be public and accessible though the blockchain explorer for every person that can access to it.

#### <a name="step4"></a>4.- Integrate the interface with the contracts

We will add polkadotJs and we are going to generate all the posible interactions to the contract. On one side we will have the creation options that will be filled in order to create a new contract, and in the other side we will have all the contract interactions that will be also divided in two. One for changing the options in the contract and the other for claiming the payments that are already released.
Once the treasury has its own worth, the only way to spend that treasury will be by the claim of the beneficiaries, so that will warranty is not going to be spendables.

#### <a name="step5"></a>5.- Quality Assurance

We will be focusing on security and usability, checking the functionality all over the UX.
There will be a suite for automated testing including happy paths and edge cases.

#### <a name="step6"></a>6.- Build a Dockerized deliverable

Our deliverable will be built using Docker to ensure easy reproducibility across various architectures and computers. All the necessary functionality will be containerized, making it simpler to deploy and run.

#### <a name="step7"></a>7.- Write project documentation

We will provide the documentation including a video of how to run the tool and an otherone to describe how to create a payroll contract from the ui and showing how to claim the amount released on a period of time.

### Ecosystem Fit

A transparent payroll smart contract fits into the Polkadot/Kusama ecosystem by being built on one of the independent blockchains connected to the Polkadot network. The smart contract will be used to automate and secure payroll transactions between diffent actors, with all information being recorded transparently on the blockchain.

By utilizing the Polkadot network, the payroll smart contract can benefit from the security and scalability of blockchain technology, while also being able to communicate and transact with other chains and technologies in a decentralized and trustless way. Ultimately, this could lead to a more efficient and transparent payroll system that empowers both employers and employees in a completely decentralized web where users are in control.

Help us locate your project in the Polkadot/Substrate/Kusama landscape and what problems it tries to solve by answering each of these questions:

- Where and how does your project fit into the ecosystem?
  As far as we can tell there is no work being done by the community in this type of solutions and we believe this is a commonn enough problem that a good community solution could help us catch up to other blockchains that already have mature solutions present.
- Who is your target audience (parachain/dapp/wallet/UI developers, designers, your own user base, some dapp's userbase, yourself)?
  See [User Personas](#user_personas)
- What need(s) does your project meet?
  We believe there are a lot of small projects in the polkadot space that require recurring payments for services and that those are currently done outside the ecosystem. This project would create a way to make those payment within the polkadot/kusama umbrella with good ui, making it simple for newbie orgs to use it.
- Are there any other projects similar to yours in the Substrate / Polkadot / Kusama ecosystem?
  It has some passing similarities with opengov and treasury, but our project is a smart contract instead of a pallet and is geared towards a much more simple use case.
  We found a lot of similar use cases in https://superfluid.finance, https://www.request.finance, https://deel.com [CHECK THIS]

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

We don't have a legal structure. We are a group of developers that want to build together. Probably we will create a legal structure for future projects. We plan on dogfooding the project and make our payments through the smart contract we are building

### Team's experience

//TODO Add some more info of the academy
We know each other from different places but we began working together at the Polkadot Blockchain Academy 2023 in Buenos Aires, Argentina. We formed a tight knit study group and helped each other to better navigate the Academy's teaching and to complete the myriad of coding assignments we needed to do in order to get certified as a Blockchain developer, which we all accomplished.

Here are some brief backgrounds on each of us:

- Ezequiel has experience as a CTO of an latam edtech with 60k paying users. He has worked as Engineering Director in Rappi managing over 50 developers. Has a lot of previous experience as a backend dev and as devops.
- Gabriel, Luca and Tomas are advocates from The Graph Protocol. They have experience building subgraphs for different projects including CowSwap, MakerDAO and Lens protocol.
- At the Latam Hackathon of Polkadot (https://polkadothackathonlatam.com), Gabriel and Luca won first place in the Web3/Blockchain Tooling category with their project (https://polkadothackathonlatam.com/proyecto-inner/LactobaciloGG/usuario-single/).
- Tomas is a full-stack and Solidity developer with several years of experience.

### Team Code Repos

- https://github.com/protofire/messari-subgraphs
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

//TODO Link de FIGMA y breve explicacion de como funciona

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

- **Total Estimated Duration:** 2 months
- **Full-Time Equivalent (FTE):** 2 FTE
- **Total Costs:** 20,000 USD

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

After the completion of this project, we would love to broaden its scope.

//TODO Add plans and explain better
**Multiple Assets**

- Add support for payment in multiple assets

**Cover Different Scenarios**

- Provide smart contracts for different scenarios such as payment for recurring services, payment for a specific amount of time, etc.

## Referral Program (optional) :moneybag:

You can find more information about the program [here](../README.md#moneybag-referral-program).

//TODO Add referral Pepe

- **Referrer:** Name of the Polkadot Ambassador or GitHub account of the Web3 Foundation grantee
- **Payment Address:** BTC, Ethereum (USDT/USDC/DAI) or Polkadot/Kusama (aUSD) payment address. Please also specify the currency. (e.g. 0x8920... (DAI))

## Additional Information :heavy_plus_sign:

**How did you hear about the Grants Program?** Polkadot Blockchain Academy
