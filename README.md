# 🏦 Simplified Account Simulation

A basic Python class designed for educational purposes to simulate the core functionality of a bank account, including initialization and withdrawal logic.

---

## ✨ Features

* **Initialization:**
* **Withdrawal:** Safely simulate withdrawing funds with checks for **insufficient funds** and **negative/zero amounts**.


### Prerequisites

You need to have **Python 3** installed on your system.

### Code

Save the following code as a file named `account.py`:

```python
class Account:
   
    def __init__(self, balance):
        # Initialize the account with the starting balance
        self.balance = balance
        
    def withdraw(self, amount):
        """
        Simulates withdrawing an amount from the account balance.
        
        Args:
            amount (float): The amount to be withdrawn.
            
        Returns:
            bool: True if the withdrawal was successful, False otherwise.
        """
        if amount > self.balance:
            print("Error: Insufficient funds.")
            return False
        elif amount <= 0:
            print(" Error: Withdrawal amount must be positive.")
            return False
        else:
            # Perform the successful withdrawal
            self.balance -= amount
            print(f" Successful withdrawal of ${amount:.2f}.")
            print(f"Current balance: ${self.balance:.2f}.")
            return True

# --- Example Usage (Simulation Only) ---
my_simulated_account = Account(balance=500.00)

print("\n--- Attempt 1: Valid Withdrawal ---")
my_simulated_account.withdraw(150.00)

print("\n--- Attempt 2: Invalid (Insufficient Funds) ---")
# Attempts to withdraw 400.00 from a balance of 350.00
my_simulated_account.withdraw(400.00)
