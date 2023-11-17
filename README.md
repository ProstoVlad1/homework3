class Pet:
    def __init__(self, name, species):
        self.name = name
        self.species = species
        self.energy = 100

    def sleep(self, hours):
        self.energy += hours * 10
        print(f"{self.name} is sleeping. Energy is now {self.energy}.")

    def play(self, hours):
        if self.energy >= hours * 5:
            self.energy -= hours * 5
            print(f"{self.name} is playing. Energy is now {self.energy}.")
        else:
            print(f"{self.name} is too tired to play.")

class Person:
    def __init__(self, name):
        self.name = name

    def interact_with_pet(self, pet, activity, hours):
        if activity == 'sleep':
            pet.sleep(hours)
        elif activity == 'play':
            pet.play(hours)
        else:
            print(f"{self.name} doesn't know how to {activity} with {pet.name}.")


cat = Pet("cookie", "Cat")
dog = Pet("bob", "Dog")

person = Person("Alice")

person.interact_with_pet(cat, 'sleep', 3)
person.interact_with_pet(dog, 'play', 2)
person.interact_with_pet(cat, 'play', 2)
person.interact_with_pet(dog, 'sleep', 3)
