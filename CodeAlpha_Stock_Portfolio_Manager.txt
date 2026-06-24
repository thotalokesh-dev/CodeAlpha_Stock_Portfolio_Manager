stocks = {
    "AAPL": 180,
    "TSLA": 250,
    "GOOG": 150,
    "MSFT": 350
}

portfolio = {}

print("===== STOCK PORTFOLIO TRACKER =====")

n = int(input("Enter Number of Stocks: "))

for i in range(n):
    stock = input("Enter Stock Symbol: ").upper()

    if stock not in stocks:
        print("Stock Not Available")
        continue

    qty = int(input("Enter Quantity: "))
    portfolio[stock] = qty

total = 0

print("\n------ PORTFOLIO SUMMARY ------")
print("Stock\tQty\tPrice\tValue")

for stock, qty in portfolio.items():
    value = qty * stocks[stock]
    total += value

    print(f"{stock}\t{qty}\t{stocks[stock]}\t{value}")

print("\nTotal Portfolio Value = $", total)

with open("portfolio_report.txt", "w") as file:
    file.write("Portfolio Report\n")
    file.write(f"Total Value = ${total}")

print("Report Saved Successfully!")