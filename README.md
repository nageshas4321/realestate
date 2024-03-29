**RealEstate Smart Contract**

---

**Overview**

The RealEstate smart contract is designed to facilitate the buying process of a property in a decentralized and transparent manner on the Ethereum blockchain. It allows potential buyers to approve the purchase and ensures that they meet certain eligibility criteria before proceeding with the transaction.

---

**Contract Details**

- **SPDX-License-Identifier**: MIT
- **Solidity Version**: ^0.8.0

---

**Functions**

1. **purchaseProperty(uint256 _buyersApproval, uint256 _propertyValue) external**
   - This function is called by potential buyers to approve the purchase of the property.
   - Parameters:
     - _buyersApproval: Number of buyers who approve the purchase.
     - _propertyValue: Value of the property being purchased.
   - Actions:
     - Sets the buyersCount to the provided _buyersApproval.
     - Asserts that the _propertyValue is greater than 0.
     - Reverts the transaction if the _buyersApproval is less than 5, indicating that the property requires approval from a minimum of 5 buyers.

2. **buyerEligibility(uint256 _buyerIncome) external pure**
   - This function is used to check the eligibility of a potential buyer based on their income.
   - Parameters:
     - _buyerIncome: Income of the potential buyer.
   - Actions:
     - Requires that the _buyerIncome is at least $50,000.
     - The function is marked as pure, indicating that it does not modify the contract's state.

---

**Readme**

**Getting Started**

To interact with the RealEstate smart contract, you'll need an Ethereum wallet and access to an Ethereum-enabled browser such as MetaMask.

**Usage**

1. **Approving the Purchase**
   - Call the `purchaseProperty` function with the desired number of buyer approvals and the property value.
   - Ensure that the property value is greater than 0.
   - Ensure that the number of buyer approvals is at least 5.

2. **Checking Buyer Eligibility**
   - Before calling the `purchaseProperty` function, use the `buyerEligibility` function to verify the buyer's income eligibility.
   - Provide the potential buyer's income as an argument to the function.
   - Ensure that the buyer's income is at least $50,000.

**License**

This project is licensed under the terms of the MIT license.
