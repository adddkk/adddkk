- 👋 Hi, I’m @adddkk
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...

<!---
adddkk/adddkk is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
class Country:
    def __init__(self, troops, money):
        self.troops = troops
        self.money = money

    def calculate_score(self):
        return self.troops + self.money

    def __str__(self):
        return f"Troops: {self.troops}, Money: {self.money}"

# Define the countries
america = Country(5000, 100)
russia = Country(3000, 150)
china = Country(4000, 50)
north_korea = Country(2000, 0)
england = Country(1000, 90)

# Define a function to determine the winner of a war
def determine_winner(country1, country2):
    score1 = country1.calculate_score()
    score2 = country2.calculate_score()

    if score1 > score2:
        return country1
    elif score2 > score1:
        return country2
    else:
        return None

# Define a function to simulate a war between two countries
def simulate_war(country1, country2):
    winner = determine_winner(country1, country2)

    if winner:
        winner.troops += country2.troops
        winner.money += country2.money

        del country2

# Simulate the first war between America and England with the support of North Korea
simulate_war(america, england)
simulate_war(america, north_korea)

# Simulate the second war between China and Russia
simulate_war(china, russia)

# Determine the winner of the third war
winner_third_war = determine_winner(america, china)

print("The winner of the third war is:", winner_third_war)

