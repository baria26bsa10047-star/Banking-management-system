# SOFTWARE REQUIREMENT SPECIFICATION
**Console Banking Program**  
**Document ID:** SRS-BNK-001  
**Language:** Python 
 

---

## 1. PROBLEM STATEMENT
Modern individuals require simple, accessible, and error-proof tools to manage personal day-to-day financial transactions. Traditional banking systems are often complex, requiring heavy infrastructure or overhead for basic logic validation.

The primary objective of this project is to develop a lightweight, terminal-based banking application that enables users to perform fundamental financial operations—specifically viewing current account balances, depositing funds, and withdrawing funds—while enforcing strict validation controls against invalid inputs such as negative amounts or overdrawing available capital.

---

## 2. SCOPE OF THE PROJECT

### In-Scope Functionality
* Real-time balance tracking during session execution.
* Safe cash deposit processing with positivity check.
* Fund withdrawal verification against current balance.
* Interactive, menu-driven CLI interface.
* Graceful exit handling and input error management.

### Out-of-Scope (Future Releases)
* Persistent database storage (state resets on exit).
* Multi-user authentication or account switching.
* Transaction history logging and export.
* Interest calculation or multi-currency support.

---

## 3. TARGET USERS
The terminal application is tailored for specific user personas and educational deployment environments:

| User Role | Primary Needs | Interface Mode |
| :--- | :--- | :--- |
| **Individual User** | Quickly track temporary balances and model daily cash flows. | Command Line (CLI) |
| **Python Student / Trainee** | Understand standard program loops, conditional routing, and state manipulation. | Source Code / Terminal |
| **System Administrator** | Lightweight tool for testing basic algorithmic logic in non-GUI environments. | Headless Shell |

---

## 4. HIGH-LEVEL FEATURES
1. Balance Display (`show_balance`)
2. Deposit Processing (`deposit`)
3. Withdrawal Processing (`withdraw`)
4. Main Loop & User Options (`main`)

---

## 5. FUNCTIONAL REQUIREMENTS & VALIDATION RULES

| Operation | Input Condition | System Response | Status Code |
| :--- | :--- | :--- | :--- |
| **Deposit** | $\text{amount} < 0$ | Display "That's not a valid amount" | REJECTED |
| **Deposit** | $\text{amount} \ge 0$ | Add amount to balance | APPROVED |
| **Withdraw** | $\text{amount} > \text{balance}$ | Display "Insufficient funds" | REJECTED |
| **Withdraw** | $\text{amount} < 0$ | Display "Amount must be greater than 0" | REJECTED |
| **Withdraw** | $0 \le \text{amount} \le \text{balance}$ | Deduct amount from balance | APPROVED |

---
