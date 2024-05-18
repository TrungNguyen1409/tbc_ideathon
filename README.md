
<img width="1025" alt="image" src="https://github.com/TrungNguyen1409/tbc_ideathon/assets/96893597/37193f1e-cc15-40c8-b44f-12d3bd035ba1">

# AgriSafe - Blockchain Insurance Project

## Overview

AgriSafe is an innovative insurance system built on the blockchain that provides autonomous insurance payments when specific conditions are met. This project leverages weather data fetched from the SUI Oracle Weather service to trigger insurance payouts automatically, ensuring transparency, security, and efficiency.

## Features

- **Decentralized Insurance**: Provides insurance policies on the blockchain.
- **Autonomous Payments**: Automatically triggers insurance payouts based on predefined weather conditions.
- **Weather Data Integration**: Uses data from SUI Oracle Weather to determine if conditions for payouts are met.
- **Smart Contracts**: Implements the core logic for policy management and payouts using smart contracts.
- **Transparency and Security**: Ensures that all transactions and conditions are transparent and secure due to blockchain technology.

## Prerequisites

- Node.js
- npm or yarn
- Hardhat (Ethereum development environment)
- Solidity (for writing smart contracts)
- Web3.js (for interacting with the blockchain)
- Metamask (or any other Ethereum wallet)

## Installation

1. **Clone the Repository**

    ```bash
    git clone https://github.com/yourusername/agrisafe.git
    cd agrisafe
    ```

2. **Install Dependencies**

    ```bash
    npm install
    ```

    or

    ```bash
    yarn install
    ```

3. **Compile Smart Contracts**

    ```bash
    npx hardhat compile
    ```

4. **Deploy Smart Contracts**

    Update the deployment script located in `scripts/deploy.js` with your deployment parameters.

    ```bash
    npx hardhat run scripts/deploy.js --network yourNetwork
    ```

## Usage

1. **Running the Application**

    Start the local development server:

    ```bash
    npm start
    ```

2. **Interacting with Smart Contracts**

    Use the web interface to interact with the deployed smart contracts. Ensure you have a web3-enabled browser or extension (e.g., Metamask) connected to the appropriate network.

3. **Fetching Weather Data**

    The smart contracts will automatically fetch weather data from SUI Oracle Weather. Ensure you have the correct API keys and endpoints configured in your project settings.

## Project Structure

- `contracts/`: Contains the Solidity smart contracts.
- `scripts/`: Deployment scripts.
- `test/`: Test scripts for smart contracts.
- `src/`: Frontend source code.
- `config/`: Configuration files.

## Smart Contracts

### InsurancePolicy.sol

This contract manages the insurance policies.

- **Functions**:
  - `createPolicy()`: Creates a new insurance policy.
  - `checkPolicyCondition()`: Checks if the conditions for the policy are met.
  - `payout()`: Executes the payout if conditions are met.

### OracleConsumer.sol

This contract interacts with the SUI Oracle Weather to fetch weather data.

- **Functions**:
  - `requestWeatherData()`: Requests weather data from the oracle.
  - `receiveWeatherData()`: Callback function to handle data received from the oracle.

## Configuration

### API Keys

Ensure your API keys for SUI Oracle Weather are set in the `.env` file:

```env
SUI_ORACLE_API_KEY=your_api_key
NETWORK_URL=https://mainnet.infura.io/v3/your_infura_project_id
PRIVATE_KEY=your_private_key
```

### Network Configuration

Update the network configuration in `hardhat.config.js`:

```js
module.exports = {
  networks: {
    yourNetwork: {
      url: process.env.NETWORK_URL,
      accounts: [process.env.PRIVATE_KEY]
    }
  },
  solidity: "0.8.4",
};
```

## Testing

1. **Run Tests**

    ```bash
    npx hardhat test
    ```

2. **Test Coverage**

    ```bash
    npx hardhat coverage
    ```

## Contributing

We welcome contributions! Please read our [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines on how to proceed.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Contact

For any questions or support, please reach out to us at support@agrisafe.com.

---

Thank you for using AgriSafe! We hope it serves your needs effectively.
