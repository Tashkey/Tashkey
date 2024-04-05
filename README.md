class Budget:
    def __init__(self, initial_balance=0):
        self.balance = initial_balance
        self.expenses = {}

    def add_income(self, amount):
        """Add income to the budget."""
        self.balance += amount

    def add_expense(self, category, amount):
        """Add an expense to the budget."""
        if category in self.expenses:
            self.expenses[category] += amount
        else:
            self.expenses[category] = amount
        self.balance -= amount

    def get_balance(self):
        """Get the current balance."""
        return self.balance

    def get_expenses(self):
        """Get a summary of expenses by category."""
        return self.expenses

    def __str__(self):
        """Print a summary of the budget."""
        summary = f"Budget Summary:\nBalance: ${self.balance:.2f}\n"
        for category, amount in self.expenses.items():
            summary += f"{category}: ${amount:.2f}\n"
        return summary

# Example usage:
my_budget = Budget(initial_balance=1000)
my_budget.add_income(2000)
my_budget.add_expense("Groceries", 150)
my_budget.add_expense("Rent", 800)
print(my_budget)
