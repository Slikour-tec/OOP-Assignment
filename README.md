# OOP-Assignment

# Activity 1: Design Your Own Class
class Smartphone:
    def __init__(self, brand, model, battery_life):
        self.brand = brand
        self.model = model
        self.__battery_life = battery_life  # Encapsulated attribute
    
    def make_call(self, number):
        print(f"Calling {number} from {self.model}...")
    
    def battery_status(self):
        print(f"Battery life: {self.__battery_life}%")
    
    def charge(self, amount):
        self.__battery_life = min(100, self.__battery_life + amount)
        print(f"Charging... Battery now at {self.__battery_life}%")

# Inheritance Example
class GamingPhone(Smartphone):
    def __init__(self, brand, model, battery_life, cooling_system):
        super().__init__(brand, model, battery_life)
        self.cooling_system = cooling_system
    
    def game_mode(self):
        print(f"{self.model} is now in gaming mode with {self.cooling_system} cooling!")

# Creating objects
phone1 = Smartphone("Apple", "iPhone 14", 80)
gaming_phone = GamingPhone("Asus", "ROG Phone 6", 90, "Advanced Liquid Cooling")

phone1.make_call("123-456-7890")
phone1.battery_status()
gaming_phone.game_mode()

gaming_phone.charge(15)

def separator():
    print("\n" + "-"*40 + "\n")

separator()

# Activity 2: Polymorphism Challenge
class Vehicle:
    def move(self):
        pass  # Abstract method (will be overridden)

class Car(Vehicle):
    def move(self):
        print("Driving 🚗")

class Plane(Vehicle):
    def move(self):
        print("Flying ✈️")

class Boat(Vehicle):
    def move(self):
        print("Sailing 🚢")

# Polymorphism in action
vehicles = [Car(), Plane(),Boat()]
for v in vehicles:
