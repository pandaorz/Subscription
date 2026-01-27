# Subscription & Bookkeeping Assistant

A personal finance management system designed to work with AI Agents. This project helps you track expenses, manage subscriptions, and perform financial analysis using natural language.

## 🌟 Key Features

*   **Natural Language Entry**: Record expenses by simply telling the Agent what you spent (e.g., "Spent 800 on lunch").
*   **Subscription Management**: Keep track of recurring bills, payment dates, and education costs in a structured Markdown file.
*   **Financial Analysis**: Ask complex questions about your finances, such as "What is the education cost ratio?" or "Forecast next month's cash flow."
*   **Privacy Focused**: Designed to run locally with strict separation of sensitive data.

## 📂 Project Structure

*   **[`expenses.csv`](./expenses.csv)**: The ledger for all your daily transactions.
*   **[`subscriptions.md`](./subscriptions.md)**: The central database for recurring subscriptions, utilities, and education costs.
*   **[`bookkeeping_guide.md`](./bookkeeping_guide.md)**: A comprehensive guide on how to interact with the Agent, including command examples for various scenarios.

## 🚀 Getting Started

### 1. Recording an Expense
Simply type a command like:
> "Agent, I paid 800 NTD for the child's lunch today using family cash. Note: Feb Lunch."

The Agent will parse this into `expenses.csv`.

### 2. Checking Subscriptions
To see what's coming up:
> "Check `subscriptions.md` for any bills due in the next 10 days."

### 3. Financial Analysis
To understand your spending:
> "Analyze the total education spend for this year based on `expenses.csv` and compare it with the budget in `subscriptions.md`."

## 📖 Documentation

For detailed instructions on all available commands and workflows, please refer to [**Agent Bookkeeping Guide**](./bookkeeping_guide.md).

## 📄 License

Individual Use / Private
