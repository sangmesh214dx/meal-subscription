# Meal Subscription 

## Overview

This Solidity smart contract, named `MealSubscription`, enables users to subscribe to a meal service for a specified duration by making payments in cryptocurrency. The contract is designed to manage subscription payments and enforce certain validation rules to ensure secure and fair transactions.

## License

This smart contract is licensed under the MIT License. Please refer to the SPDX-License-Identifier at the beginning of the source code for more details.

## Contract Details

### State Variables

- `subscriber`: Address of the subscriber who deploys the contract.
- `subscriptionPayments`: Mapping to store the subscription payments made by each subscriber.

### Constructor

- The contract constructor sets the `subscriber` variable to the address of the account that deploys the contract.

### Functions

#### `subscribe(uint256 months, uint256 paymentAmount) public`

- Allows a user to subscribe to the meal service by specifying the duration (`months`) and making a payment (`paymentAmount`).
- Validation checks using `require()`:
  - Ensures that only the subscriber can invoke the `subscribe` function.
- Assertion using `assert()`:
  - Specifies a minimum subscription duration of three months (`months >= 3`).
- Conditional check:
  - If the payment amount is less than 100, the function reverts with an "Insufficient payment for subscription" message.
- Process subscription:
  - Adds the payment amount to the subscriber's total subscription payments.

## Usage

1. Deploy the smart contract to an Ethereum environment.
2. Call the `subscribe` function with the desired subscription duration (`months`) and payment amount (`paymentAmount`).
3. Ensure that the caller is the subscriber account.
4. Observe the updated `subscriptionPayments` mapping with the subscriber's address and the corresponding payment amount.

## Example

```solidity
// Deploy the MealSubscription contract
MealSubscription mealSubscription = new MealSubscription();

// Subscribe to the meal service for 6 months with a payment of 150 units
mealSubscription.subscribe(6, 150);

// Check the subscription payment for the caller
uint256 payment = mealSubscription.subscriptionPayments(msg.sender);
```
## Author 

Sangmesh M

sangmeshm42@gmail.com
