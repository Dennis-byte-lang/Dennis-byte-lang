import time

class PoultryFarm:
    def __init__(self, total_birds, feed_capacity, water_capacity):
        self.total_birds = total_birds
        self.feed_capacity = feed_capacity  # Total feed available (kg)
        self.water_capacity = water_capacity  # Total water available (liters)
        self.feed_consumption_per_bird = 0.15  # kg of feed per bird per day
        self.water_consumption_per_bird = 0.25  # liters of water per bird per day

    def daily_consumption(self):
        # Total daily consumption by all birds
        total_feed_required = self.total_birds * self.feed_consumption_per_bird
        total_water_required = self.total_birds * self.water_consumption_per_bird
        return total_feed_required, total_water_required

    def feed_and_water(self):
        # Simulate the feeding and watering process
        feed_required, water_required = self.daily_consumption()
        
        if self.feed_capacity >= feed_required and self.water_capacity >= water_required:
            self.feed_capacity -= feed_required
            self.water_capacity -= water_required
            print(f"Feeding {self.total_birds} birds.")
            print(f"Remaining feed: {self.feed_capacity:.2f} kg")
            print(f"Remaining water: {self.water_capacity:.2f} liters")
        else:
            print("Warning: Not enough feed or water available.")
            self.restock()

    def restock(self):
        # Simulate restocking feed and water (for demonstration purposes)
        print("Restocking feed and water...")
        self.feed_capacity += 50  # Add 50 kg of feed
        self.water_capacity += 100  # Add 100 liters of water
        print(f"New feed capacity: {self.feed_capacity:.2f} kg")
        print(f"New water capacity: {self.water_capacity:.2f} liters")

    def run_farm(self, days):
        for day in range(1, days + 1):
            print(f"\n--- Day {day} ---")
            self.feed_and_water()
            time.sleep(1)  # Simulate daily operation (can be removed for testing)


# Example Usage
total_birds = 100
initial_feed = 200  # kg
initial_water = 300  # liters

farm = PoultryFarm(total_birds, initial_feed, initial_water)
farm.run_farm(7)  # Simulate farm operations for 7 days

<!---
Dennis-byte-lang/Dennis-byte-lang is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
