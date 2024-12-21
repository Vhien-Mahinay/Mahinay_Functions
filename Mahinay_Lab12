def display_menu(menu):
    print("\n--- Menu ---")
    for item, price in menu.items():
        print(f"{item}: PHP {price:.2f}")

def calculate_total(menu, selected_items):
    total = 0
    for item, quantity in selected_items.items():
        total += menu[item] * quantity
    return total

def process_payment(total_cost):
    while True:
        try:
            cash_rendered = float(input("Enter cash amount: PHP "))
            if cash_rendered >= total_cost:
                return cash_rendered
            else:
                print("Insufficient cash. Please enter an amount equal to or greater than the total cost.")
        except ValueError:
            print("Invalid input. Please enter a numeric value.")

def main():
    # Menu items with prices
    menu = {
        "Burger": 75.00,
        "Pizza": 150.00,
        "Pasta": 120.00,
        "Fries": 50.00,
        "Soft Drink": 30.00,
        "Ice Cream": 45.00
    }

    display_menu(menu)

    # Order selection
    selected_items = {}
    while True:
        selected_item = input("\nEnter the item you'd like to order (or type 'done' to finish): ")
        if selected_item.lower() == 'done':
            break
        if selected_item in menu:
            while True:
                try:
                    quantity = int(input(f"Enter quantity for {selected_item}: "))
                    if quantity > 0:
                        selected_items[selected_item] = selected_items.get(selected_item, 0) + quantity
                        break
                    else:
                        print("Quantity must be greater than 0.")
                except ValueError:
                    print("Invalid input. Please enter a numeric value.")
        else:
            print("Invalid choice. Please select an item from the menu.")

    if not selected_items:
        print("\nNo items selected. Thank you!")
        return

    total_cost = calculate_total(menu, selected_items)
    print("\nYou ordered:")
    for item, quantity in selected_items.items():
        print(f"{item} x{quantity} = PHP {menu[item] * quantity:.2f}")
    print(f"Total cost: PHP {total_cost:.2f}")

    # Payment processing
    cash_rendered = process_payment(total_cost)
    change = cash_rendered - total_cost
    print(f"\nPayment successful! Change: PHP {change:.2f}")
    print("Thank you for your order!")

if __name__ == "__main__":
    main()


