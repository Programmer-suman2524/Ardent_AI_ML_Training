import statistics


def get_numbers(prompt="Enter numbers separated by spaces: "):
    """Helper to get multiple numbers from user."""
    while True:
        try:
            raw = input(prompt)
            numbers = list(map(float, raw.strip().split()))
            if not numbers:
                print("  ⚠  Please enter at least one number.")
                continue
            return numbers
        except ValueError:
            print("  ⚠  Invalid input. Please enter numeric values only.")


def get_two_numbers():
    """Helper to get exactly two numbers from user."""
    while True:
        try:
            a = float(input("  Enter first number : "))
            b = float(input("  Enter second number: "))
            return a, b
        except ValueError:
            print("  ⚠  Invalid input. Please enter numeric values.")


def fmt(n):
    """Format number: show int if whole, else float."""
    return int(n) if isinstance(n, float) and n.is_integer() else round(n, 6)


# ─── Operations ───────────────────────────────────────────────────────────────

def add():
    a, b = get_two_numbers()
    print(f"\n  ✅  {fmt(a)} + {fmt(b)} = {fmt(a + b)}\n")

def subtract():
    a, b = get_two_numbers()
    print(f"\n  ✅  {fmt(a)} - {fmt(b)} = {fmt(a - b)}\n")

def multiply():
    a, b = get_two_numbers()
    print(f"\n  ✅  {fmt(a)} × {fmt(b)} = {fmt(a * b)}\n")

def divide():
    a, b = get_two_numbers()
    if b == 0:
        print("\n  ❌  Error: Division by zero is undefined.\n")
    else:
        print(f"\n  ✅  {fmt(a)} ÷ {fmt(b)} = {fmt(a / b)}\n")

def modulo():
    a, b = get_two_numbers()
    if b == 0:
        print("\n  ❌  Error: Modulo by zero is undefined.\n")
    else:
        print(f"\n  ✅  {fmt(a)} % {fmt(b)} = {fmt(a % b)}\n")

def mean_calc():
    nums = get_numbers()
    result = statistics.mean(nums)
    print(f"\n  ✅  Numbers : {[fmt(n) for n in nums]}")
    print(f"      Mean    : {fmt(result)}\n")

def median_calc():
    nums = get_numbers()
    result = statistics.median(nums)
    print(f"\n  ✅  Numbers : {sorted([fmt(n) for n in nums])}")
    print(f"      Median  : {fmt(result)}\n")

def mode_calc():
    nums = get_numbers()
    try:
        result = statistics.mode(nums)
        print(f"\n  ✅  Numbers : {[fmt(n) for n in nums]}")
        print(f"      Mode    : {fmt(result)}\n")
    except statistics.StatisticsError:
        # multimode available in Python 3.8+
        modes = statistics.multimode(nums)
        print(f"\n  ✅  Numbers : {[fmt(n) for n in nums]}")
        print(f"      Modes   : {[fmt(m) for m in modes]} (multiple modes)\n")

def average_calc():
    nums = get_numbers()
    result = sum(nums) / len(nums)
    print(f"\n  ✅  Numbers : {[fmt(n) for n in nums]}")
    print(f"      Average : {fmt(result)}\n")


# ─── Menu ─────────────────────────────────────────────────────────────────────

MENU = """
┌─────────────────────────────────────┐
│         SELECT AN OPERATION         │
├────┬────────────────────────────────┤
│  1 │  Addition          ( a + b )   │
│  2 │  Subtraction       ( a - b )   │
│  3 │  Multiplication    ( a × b )   │
│  4 │  Division          ( a ÷ b )   │
│  5 │  Modulo            ( a % b )   │
├────┼────────────────────────────────┤
│  6 │  Mean              (list)      │
│  7 │  Median            (list)      │
│  8 │  Mode              (list)      │
│  9 │  Average           (list)      │
├────┼────────────────────────────────┤
│  0 │  Exit                          │
└────┴────────────────────────────────┘
"""

OPERATIONS = {
    "1": add,
    "2": subtract,
    "3": multiply,
    "4": divide,
    "5": modulo,
    "6": mean_calc,
    "7": median_calc,
    "8": mode_calc,
    "9": average_calc,
}


def main():
    print(__doc__)
    while True:
        print(MENU)
        choice = input("  ➤  Your choice: ").strip()

        if choice == "0":
            print("\n  👋  Goodbye!\n")
            break
        elif choice in OPERATIONS:
            OPERATIONS[choice]()
        else:
            print("\n  ⚠  Invalid choice. Please enter a number from 0–9.\n")


if __name__ == "__main__":
    main()
