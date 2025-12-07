# Mobile Repair Shop Billing System

def main():
    # Read number of devices
    while True:
        try:
            N = int(input("Enter number of devices to repair: "))
            if N <= 0:
                print("Please enter a positive number!")
                continue
            break
        except ValueError:
            print("Invalid input! Please enter a valid number.")

    total_cost = 0.0
    discount_count = 0

    # Process each device
    for i in range(1, N + 1):
        print(f"\n--- Device {i} ---")
        
        # Read repair cost
        while True:
            try:
                cost = float(input("Enter repair cost: ₹"))
                if cost < 0:
                    print("Cost cannot be negative!")
                    continue
                break
            except ValueError:
                print("Invalid input! Please enter a valid amount.")

        # Apply discount if applicable
        if cost > 3000:
            discount = cost * 0.05
            final_cost = cost - discount
            discount_count += 1
            print(f"✓ 5% discount applied: ₹{discount:.2f}")
            print(f"  Final cost after discount: ₹{final_cost:.2f}")
        else:
            final_cost = cost
            print(f"  No discount applied")

        # Add to total
        total_cost += final_cost

    # Print summary
    print("\n" + "=" * 40)
    print("REPAIR SUMMARY")
    print("=" * 40)
    print(f"Total devices repaired: {N}")
    print(f"Total bill amount: ₹{total_cost:.2f}")
    print(f"Discounts given: {discount_count}")
    print("=" * 40)

if __name__ == "__main__":
    main()
