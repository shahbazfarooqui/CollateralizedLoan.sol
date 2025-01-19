# CollateralizedLoan.sol

# Collateralized Loan Smart Contract

This repository contains the Solidity smart contract for a collateralized loan system. It facilitates a secure lending process where one party (borrower) can take a loan from another party (lender) by locking a specified amount of collateral. If the borrower fails to repay the loan within the defined time period, the collateral is automatically transferred to the lender.

## Features
- **Collateral Locking**: The borrower deposits collateral in the form of an ERC-20 token (e.g., BNB) which is held in the contract.
- **Loan Disbursement**: The lender transfers the loan amount (in USDT or other ERC-20 token) to the borrower.
- **Loan Repayment**: The borrower can repay the loan within the defined period to retrieve their collateral.
- **Collateral Forfeiture**: If the borrower fails to repay the loan within the deadline, the collateral is automatically transferred to the lender.

## Contract Overview
The contract includes the following key functions:

1. **depositCollateral**: Allows the borrower to deposit collateral into the smart contract.
2. **giveLoan**: Allows the lender to transfer the loan amount to the borrower.
3. **repayLoan**: Allows the borrower to repay the loan within the deadline to retrieve their collateral.
4. **claimCollateral**: Allows the lender to claim the collateral if the borrower fails to repay within the deadline.

## How It Works
1. **Initialization**: Deploy the contract by specifying the addresses of:
   - Borrower (partyA)
   - Lender (partyB)
   - USDT token contract
   - BNB token contract
   - Loan amount
   - Collateral amount

2. **Deposit Collateral**: The borrower deposits the collateral by calling `depositCollateral`.

3. **Loan Transfer**: The lender transfers the loan amount to the borrower by calling `giveLoan`.

4. **Loan Repayment**:
   - The borrower repays the loan amount to the lender by calling `repayLoan`.
   - Upon successful repayment, the collateral is returned to the borrower.

5. **Collateral Claim**:
   - If the borrower fails to repay within the deadline, the lender can call `claimCollateral` to retrieve the collateral.

## Deployment
1. Deploy the contract on an Ethereum-compatible blockchain using Remix or Hardhat.
2. Provide the following constructor arguments:
   - `_partyA`: Borrower address
   - `_partyB`: Lender address
   - `_usdtTokenAddress`: ERC-20 token address for the loan (e.g., USDT)
   - `_bnbTokenAddress`: ERC-20 token address for the collateral (e.g., BNB)
   - `_loanAmount`: Loan amount (in smallest token units, e.g., 2000 USDT = 2000000)
   - `_collateralAmount`: Collateral amount (e.g., 2 BNB = 2000000000000000000 wei)

## Usage
1. **Prerequisites**:
   - Install MetaMask or any other wallet to interact with the blockchain.
   - Fund the wallet with test tokens if using a testnet.

2. **Testing on Remix**:
   - Copy the Solidity code into a new file on Remix.
   - Compile the code using the appropriate compiler version (e.g., `^0.8.0`).
   - Deploy the contract by providing the constructor arguments.

3. **Interacting with the Contract**:
   - Use the contract's functions to simulate the lending process.
   - Test different scenarios, such as loan repayment and collateral forfeiture.

## Security Considerations
- Ensure only trusted ERC-20 token contracts are used to prevent token-related vulnerabilities.
- Perform thorough testing on testnets before deploying to mainnet.
- Implement KYC and other verification measures for real-world use cases.

## License
This project is licensed under the MIT License. See the LICENSE file for details.
