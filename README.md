# sportclass Bike:
    def __init__(self, color, brand):
        self.color = color
        self.brand = brand
        self.speed = 0
        self.is_on = False

    def turn_on(self):
        if not self.is_on:
            self.is_on = True
            print("The bike is now turned on.")
        else:
            print("The bike is already turned on.")

    def turn_off(self):
        if self.is_on:
            self.is_on = False
            self.speed = 0
            print("The bike is now turned off.")
        else:
            print("The bike is already turned off.")

    def accelerate(self, amount):
        if self.is_on:
            self.speed += amount
            print(f"Accelerated! Current speed: {self.speed} km/h")
        else:
            print("Cannot accelerate. Bike is turned off.")

    def brake(self, amount):
        if self.is_on:
            self.speed = max(0, self.speed - amount)
            print(f"Braked! Current speed: {self.speed} km/h")
        else:
            print("Cannot brake. Bike is turned off.")

    def status(self):
        if self.is_on:
            print(f"The {self.color} {self.brand} bike is turned on, moving at {self.speed} km/h.")
        else:
            print(f"The {self.color} {self.brand} bike is turned off.")


# Example usage:
if __name__ == "__main__":
    my_bike = Bike(color="Red", brand="Trek")
    
    my_bike.turn_on()
    my_bike.accelerate(20)
    my_bike.brake(5)
    my_bike.status()
    
    my_bike.accelerate(15)
    my_bike.brake(10)
    my_bike.status()
    
    my_bike.turn_off()
    my_bike.status()
