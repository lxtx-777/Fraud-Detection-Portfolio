# SQL Fraud Detection Mini-Project 🛡️

## Overview

For this project I used the synthetic PaySim1 transaction dataset to explore typical fraud patterns with SQL.  
Goal: show how SQL can be used to detect suspicious behavior (mules, high-risk transfers, timing patterns) in a large transaction log.

---

## Dataset

- Source: Kaggle – Synthetic Financial Datasets For Fraud Detection (PaySim)
- Size: ~6M transactions
- Key columns: `step`, `type`, `amount`, `nameOrig`, `nameDest`, `oldbalanceOrg`, `newbalanceOrig`, `oldbalanceDest`, `newbalanceDest`, `isFraud`, `isFlaggedFraud`

> Note: The original CSV is not included in this repo due to file size limits. Please download it directly from Kaggle.

---

## SQL Techniques Used

- Filtering & sorting: `SELECT`, `WHERE`, `ORDER BY`, `LIMIT`
- Aggregations: `COUNT`, `SUM`, `AVG`, `GROUP BY`, `HAVING`
- Subqueries: `IN`, scalar subqueries in `WHERE`
- Data quality checks: arithmetic verification of balances
- Window functions: `LAG() OVER (PARTITION BY ... ORDER BY ...)` 

---

#### KEY FINDINGS from fraud aalysis ####


1. 

Fraud spikes at (steps 18, 19) and has quiet periods (steps 347, 545) where fraud drops to exactly zero. 

2. 

Bots are likely at work: I identified 112 accounts that transferred money less than 2 hours apart. S

3.

The single biggest fraud case ($10 million) makes up only 0.08% of the total loss. So... fraud cases happen in volume

4.
Average fraudulent transaction is huge (~1.4 million) compared to legitimate ones (~178k).

5.
The accounts receiving fraudulent money receive maximum two transactions. Looks like a pattern to create and dumb accounts after 2 times.

6. 
found 28 transactions marked as "Legit," even though the sender was already known as a fraudster -> Once a user is flagged, all their future moves should be blocked automatically -> adjust security filters

7.
found confusing numbers where account balance before and after a transaction doesn't match the amount sent. -> Money is disappearing, calculation glitches? bug?




## Main Queries

### 1. Time analysis of fraud (Query 6)

**Question:** At which simulation hours (`step`) do most fraud cases occur?  
**Idea:** Count fraud transactions per step and rank the busiest hours.

- Helps to spot time-based attack patterns (e.g. bursts near the end of the simulation).
- Useful as input for alerting windows or staffing decisions.

### 2. Balance integrity check (Query 7)

**Question:** Are there transactions where `oldbalanceOrg - amount` does not match `newbalanceOrig`?  
**Idea:** Recalculate the expected new balance and flag rows where the difference is larger than 0.01.

- Highlights potential system bugs or manipulation of balance fields.
- Typical first step before building any risk model: trust the data, or fix it.

### 3. Top receiving accounts / mule candidates (Query 8 & 12)

**Question:** Which destination accounts receive unusually high volume and large average payments?  
**Idea:**

- Sum all incoming amounts per `nameDest`.
- Focus on accounts with very high total volume and high average ticket size.

- These accounts often behave like *money mules*: they mainly collect and pass on funds instead of using the product normally.

### 4. Transaction volume over time (Query 9)

**Question:** How does overall traffic evolve over time?  
**Idea:** For each `step`, count transactions and sum the total amount.

- Gives a simple time-series of activity.
- Helps to put fraud spikes into context (fraud vs. normal load).

### 5. Average fraud vs. legit transaction size (Query 10)

**Question:** Are fraud transactions typically larger than normal ones?  
**Idea:** Compare `AVG(amount)` for `isFraud = 1` vs `isFraud = 0` in one result set.

- Shows whether fraudsters prefer high-value or low-value attacks.
- Can be used to argue for different thresholds in rule engines.

### 6. Cross-type anomaly: Transfers vs Cash-Out average (Query 15)

**Question:** Which `TRANSFER` transactions are larger than the average `CASH_OUT` amount?  
**Idea:** Use a subquery to get the average `CASH_OUT` value and filter all `TRANSFER` above that threshold.

- Flags transfers that are abnormally large compared to typical cash withdrawals.
- Can indicate attempts to move money quickly before cash-out.

### 7. Bad recipient fraud counts (Query 17.3)

**Question:** How many fraud transactions did each known bad recipient account have?  
**Idea:** Restrict to rows where `isFraud = 1` and count fraud transactions per `nameDest`.

- Identifies recipients that appear repeatedly in fraud cases.
- Good starting point for building a recipient watchlist.

### 8. High-frequency accounts (Window function – Query 22)

**Question:** Which accounts transact again within less than 2 hours?  
**Idea:** Use `LAG(step)` per `nameOrig` to calculate the time difference between the current and previous transaction.

- Accounts with very short gaps between transactions can be scripted or automated behavior.
- Combining this with fraud labels can help distinguish one-time attacks from “bot-style” activity.

---

## How to Use This Repo

1. Download the PaySim dataset from Kaggle and load it into a MySQL-compatible database.
2. Run `fraud_portfolio_project.sql` in your SQL client (e.g. DBeaver, Sequel Ace).


@alex
--------------------------------------------




