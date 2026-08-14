# Full-stack-security-application
Flask-based cryptocurrency transaction monitoring platform with wallet management, transfers, transaction tracking, and suspicious activity detection.
# CryptoGuard

Cryptocurrency Transaction Monitoring Platform:

CryptoGuard is a Flask-based cryptocurrency transaction platform that allows users to register, authenticate, manage cryptocurrency balances, transfer coins between users, and monitor transaction activity.

Features:

* User registration and login
* Session-based authentication
* User wallet/balance management
* Cryptocurrency transfers between users
* Transaction history
* Suspicious transaction detection
* Cryptocurrency mining/puzzle mechanism
* SQLite database integration
* User and transaction data monitoring

Tech Stack:

* **Backend:** Python, Flask
* **Database:** SQLite
* **Frontend:** HTML, CSS, JavaScript
* **Authentication:** Flask sessions

Application Flow:

```text
User
  │
  ├── Register
  │
  ├── Login
  │
  ▼
Profile / Wallet
  │
  ├── View balance
  │
  ├── Mine cryptocurrency
  │
  └── Transfer cryptocurrency
              │
              ▼
        Transaction Database
              │
              ▼
       Suspicious Check
              │
              ▼
       Transaction History
```

Core Functionality:

User Authentication:

Users can create an account using an email, username and password. After successful authentication, the username is stored in a Flask session and the user is redirected to their profile.

Wallet Management:

Each user has a cryptocurrency balance stored in the SQLite `users` database. Users can view their balance and update it through supported application operations.

Cryptocurrency Transactions:

Users can transfer cryptocurrency to another registered user.

The application:

1. Identifies the sender.
2. Retrieves the sender's balance.
3. Retrieves the receiver's balance.
4. Checks whether the sender has sufficient funds.
5. Deducts the transferred amount from the sender.
6. Adds the amount to the receiver.
7. Records the transaction.

Suspicious Transaction Detection:

Transactions contain an `is_suspicious` field. The current implementation uses a transaction-amount rule to flag suspicious transactions.

python code:
is_suspicious = amount > 5

This provides a foundation for expanding the project into a more sophisticated transaction-risk analysis system.

Mining Mechanism:

The application contains a simple mining/puzzle mechanism. Users are presented with an encoded message and receive a small cryptocurrency reward after submitting the expected decoded message.

Database:

CryptoGuard uses SQLite with two primary databases:

 Users:

Stores:

* User ID
* Email
* Username
* Password
* Cryptocurrency balance

Transactions:

Stores:

* Transaction ID
* Sender
* Receiver
* Purpose
* Amount
* Suspicious-transaction flag

Future Improvements:

* Password hashing using Werkzeug
* JWT-based authentication
* REST API architecture
* Improved transaction validation
* Configurable risk-scoring system
* Multiple suspicious-transaction detection rules
* Transaction analytics dashboard
* Blockchain API integration
* Automated unit and integration tests
* Docker deployment
* Cloud deployment


```

Author:
Syed Houzaifa

