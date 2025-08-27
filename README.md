# isat-subtask2.
# Conversion Functions

def decimal_to_binary(num: int) -> str:
    return bin(num).replace("0b", "")

def binary_to_decimal(binary_str: str) -> int:
    return int(binary_str, 2)

def decimal_to_hexadecimal(num: int) -> str:
    return hex(num).replace("0x", "").upper()

def hexadecimal_to_decimal(hex_str: str) -> int:
    return int(hex_str, 16)


# Menu Driven Program
def menu():
    while True:
        print("\n=== Conversion Menu ===")
        print("1. Convert Decimal to Binary")
        print("2. Convert Binary to Decimal")
        print("3. Convert Decimal to Hexadecimal")
        print("4. Convert Hexadecimal to Decimal")
        print("5. Exit")
        
        choice = input("Enter your choice (1-5): ")
        
        if choice == "1":
            dec = int(input("Enter a decimal number: "))
            print("Binary equivalent:", decimal_to_binary(dec))
        
        elif choice == "2":
            binary = input("Enter a binary number: ")
            print("Decimal equivalent:", binary_to_decimal(binary))
        
        elif choice == "3":
            dec = int(input("Enter a decimal number: "))
            print("Hexadecimal equivalent:", decimal_to_hexadecimal(dec))
        
        elif choice == "4":
            hexa = input("Enter a hexadecimal number: ")
            print("Decimal equivalent:", hexadecimal_to_decimal(hexa))
        
        elif choice == "5":
            print("Exiting program...")
            break
        
        else:
            print("Invalid choice! Please try again.")


# Run program
if __name__ == "__main__":
    menu()
