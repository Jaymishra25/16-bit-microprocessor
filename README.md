# 16-bit-microprocessor
class Microprocessor16Bit:
    def __init__(self):
        self.register = 0  # Initialize a 16-bit register to 0

    def load_value(self, value):
        """Load a value into the register (0-65535)."""
        if 0 <= value <= 65535:
            self.register = value
            print(f"Loaded value: {self.register}")
        else:
            print("Error: Value must be between 0 and 65535.")

    def add(self, value):
        """Add a value to the register."""
        if 0 <= value <= 65535:
            self.register = (self.register + value) & 0xFFFF  # Keep it 16-bit
            print(f"Added {value}. New register value: {self.register}")
        else:
            print("Error: Value must be between 0 and 65535.")

    def subtract(self, value):
        """Subtract a value from the register."""
        if 0 <= value <= 65535:
            self.register = (self.register - value) & 0xFFFF  # Keep it 16-bit
            print(f"Subtracted {value}. New register value: {self.register}")
        else:
            print("Error: Value must be between 0 and 65535.")

    def bitwise_and(self, value):
        """Perform bitwise AND with the register."""
        if 0 <= value <= 65535:
            self.register = self.register & value
            print(f"Bitwise AND with {value}. New register value: {self.register}")
        else:
            print("Error: Value must be between 0 and 65535.")

    def bitwise_or(self, value):
        """Perform bitwise OR with the register."""
        if 0 <= value <= 65535:
            self.register = self.register | value
            print(f"Bitwise OR with {value}. New register value: {self.register}")
        else:
            print("Error: Value must be between 0 and 65535.")

    def display_register(self):
        """Display the current value of the register."""
        print(f"Current register value: {self.register}")

def main():
    mc = Microprocessor16Bit()

    while True:
        print("\n16-Bit Microprocessor Simulator")
        print("1. Load Value")
        print("2. Add Value")
        print("3. Subtract Value")
        print("4. Bitwise AND")
        print("5. Bitwise OR")
        print("6. Display Register")
        print("7. Exit")

        choice = input("Choose an option: ")

        if choice == '1':
            value = int(input("Enter value to load (0-65535): "))
            mc.load_value(value)
        elif choice == '2':
            value = int(input("Enter value to add (0-65535): "))
            mc.add(value)
        elif choice == '3':
            value = int(input("Enter value to subtract (0-65535): "))
            mc.subtract(value)
        elif choice == '4':
            value = int(input("Enter value for bitwise AND (0-65535): "))
            mc.bitwise_and(value)
        elif choice == '5':
            value = int(input("Enter value for bitwise OR (0-65535): "))
            mc.bitwise_or(value)
        elif choice == '6':
            mc.display_register()
        elif choice == '7':
            print("Exiting the simulator.")
            break
        else:
            print("Invalid choice. Please try again.")

if __name__ == "__main__":
    main()
