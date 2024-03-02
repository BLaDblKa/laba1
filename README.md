import random

class Warrior:
    def __init__(self, name):
        self.name = name
        self.health = 100

    def attack(self, enemy):
        enemy.health -= 20
        print(f"{self.name} атакует {enemy.name}. Здоровье противника: {enemy.health}.")

# Создание двух экземпляров класса "Воин"
warrior1 = Warrior("Воин 1")
warrior2 = Warrior("Воин 2")

# Игровой цикл
while warrior1.health > 0 and warrior2.health > 0:
    attacker = random.choice([warrior1, warrior2])
    defender = warrior2 if attacker == warrior1 else warrior1
    attacker.attack(defender)

# Определение победителя
if warrior1.health <= 0 and warrior2.health <= 0:
    print("Бой закончился ничьей.")
elif warrior1.health <= 0:
    print(f"{warrior2.name} одержал победу!")
else:
    print(f"{warrior1.name} одержал победу!")
