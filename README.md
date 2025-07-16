# CipherStream: Decentralized Crypto Trade Automation

CipherStream provides a secure and decentralized framework for automated cryptocurrency trading, leveraging smart contract hooks and secure multi-party computation (MPC) key management.

CipherStream addresses the inherent risks of centralized crypto trading platforms by enabling users to execute trading strategies directly on-chain, eliminating counterparty risk and reliance on intermediaries. The core of CipherStream lies in its ability to connect user-defined trading logic to smart contract events, triggering automated trades based on predefined conditions. This allows for sophisticated strategies such as limit orders, stop-loss orders, and algorithmic trading strategies to be executed in a trustless environment. A crucial component is the secure MPC key management API, ensuring the safety and integrity of user funds while enabling automated trade execution.

The platform aims to provide a fully customizable and transparent trading experience. Users define their trading logic in Typescript, which is then compiled and deployed to the CipherStream execution environment. The system monitors relevant on-chain events and, upon fulfillment of the specified conditions, initiates trades via the secure MPC key management system. This process is completely auditable on the blockchain, guaranteeing transparency and accountability. By decentralizing trade execution and securing private keys with MPC, CipherStream offers a superior alternative to traditional, centralized crypto trading platforms.

CipherStream is designed for both individual traders and institutional investors seeking a secure and decentralized solution for automated crypto trading. Its modular architecture allows for easy integration with various DeFi protocols and exchanges, providing a flexible and extensible platform for a wide range of trading strategies. The use of TypeScript ensures type safety and maintainability, while the MPC key management system guarantees the security of user funds. Ultimately, CipherStream empowers users with the control and security needed to confidently navigate the decentralized financial landscape.

## Key Features

*   **Decentralized Trade Execution:** Executes trading strategies directly on-chain through smart contract hooks, eliminating reliance on centralized exchanges and mitigating counterparty risk. This is achieved through event listeners that monitor specific smart contract events (e.g., price changes, liquidity pool updates) and trigger trade execution when predefined conditions are met.
*   **Secure MPC Key Management API:** Implements a secure multi-party computation (MPC) key management system to protect private keys and enable automated trade execution without exposing the keys directly. This system uses a threshold signature scheme, requiring a minimum number of participants to authorize transactions, thus preventing single points of failure. The API provides primitives for key generation, signing, and recovery, all within a secure enclave.
*   **TypeScript-Based Trading Logic:** Allows users to define their trading strategies in TypeScript, providing type safety and enabling the use of modern development tools. This enables complex strategies to be defined and deployed with enhanced reliability and maintainability.
*   **Event-Driven Architecture:** Operates on an event-driven architecture, enabling real-time responses to market conditions and automated execution of trading strategies. The system utilizes a robust event processing engine that efficiently handles high volumes of on-chain events.
*   **Modular and Extensible Design:** Features a modular design that allows for easy integration with various DeFi protocols and exchanges. New connectors can be added to support different blockchains and decentralized applications.
*   **On-Chain Auditing:** All trade executions are recorded on-chain, providing a transparent and auditable record of all trading activity. This ensures accountability and allows users to verify the execution of their strategies.
*   **Gas Optimization:** Implements various gas optimization techniques to minimize transaction costs, ensuring cost-effective trading strategies. This includes batch processing of transactions and the use of gas-efficient smart contract implementations.

## Technology Stack

*   **TypeScript:** The primary programming language used for developing the CipherStream platform, ensuring type safety and maintainability.
*   **Node.js:** The runtime environment for executing the CipherStream application.
*   **Web3.js/ethers.js:** Libraries for interacting with the Ethereum blockchain and smart contracts. Web3.js or ethers.js is used to monitor smart contract events and submit transactions.
*   **Solidity:** The programming language used for writing the smart contracts that facilitate trade execution.
*   **MPC Library (e.g., tss-lib):** A library for implementing secure multi-party computation (MPC) key management. This handles key generation, signing, and recovery in a distributed and secure manner.
*   **Docker:** Used for containerizing the CipherStream application, ensuring consistent deployment across different environments.
*   **PostgreSQL:** A robust and scalable relational database used for storing trading strategies, user data, and transaction history.

## Installation

1.  **Clone the repository:**
    git clone https://github.com/jjfhwang/CipherStream.git
    cd CipherStream

2.  **Install dependencies:**
    npm install

3.  **Install dev dependencies:**
    npm install -D typescript ts-node @types/node

4.  **Compile the TypeScript code:**
    npm run build

5.  **Initialize the database:** Ensure PostgreSQL is installed and running. Create a database named `cipherstream`. Update the connection details in the configuration file. Then, run the database migration script:
    npm run migrate

## Configuration

CipherStream requires several environment variables to be configured. Create a `.env` file in the root directory of the project and add the following variables:



*   `DATABASE_URL`: The connection string for the PostgreSQL database.
*   `ETHEREUM_NODE_URL`: The URL of an Ethereum node (e.g., Infura, Alchemy) used for interacting with the blockchain.
*   `MPC_NODE_URL`: The URL of the MPC node responsible for key management. If using multiple MPC nodes, this value can be configured for each node.
*   `MPC_THRESHOLD`: The minimum number of MPC nodes required to sign a transaction.
*   `MPC_TOTAL_NODES`: The total number of MPC nodes participating in the key management system.

## Usage

Before running CipherStream, ensure that the configuration is complete and the database is properly initialized. To start the application, run the following command:

npm run start

The CipherStream API provides endpoints for creating, deploying, and managing trading strategies. The MPC key management API provides primitives for generating, signing, and recovering keys.

Example of creating a simple limit order strategy:



This example showcases a simple Typescript code that uses external client to create a limit order trading strategy that executes a trade when the price of a specified token reaches a defined threshold.

## Contributing

We welcome contributions to CipherStream. Please follow these guidelines:

1.  Fork the repository.
2.  Create a new branch for your feature or bug fix.
3.  Write clear and concise commit messages.
4.  Submit a pull request with a detailed description of your changes.
5.  Ensure your code adheres to the project's coding style and passes all tests.

## License

This project is licensed under the MIT License. See the [LICENSE](https://github.com/jjfhwang/CipherStream/blob/main/LICENSE) file for details.

## Acknowledgements

We would like to thank the open-source community for their contributions to the technologies used in this project.