# Richest Persons Analysis (2015-2024)

This project analyzes the net worth of the richest individuals from 2015 to 2024. It visualizes the changes in their wealth over the years, along with the source of their wealth. The dataset includes data for prominent figures such as Bill Gates, Jeff Bezos, Elon Musk, and Bernard Arnault.

## Dataset

The dataset consists of the following columns:

- **Year**: The year of the recorded net worth.
- **Person**: The name of the individual.
- **Net Worth (Billion USD)**: The total net worth of the individual in billions of USD.
- **Source of Wealth**: The primary source of wealth for the individual.

### Sample Data

| Year | Person          | Net Worth (Billion USD) | Source of Wealth |
|------|-----------------|-------------------------|------------------|
| 2015 | Bill Gates      | 79.2                    | Microsoft        |
| 2016 | Bill Gates      | 75.0                    | Microsoft        |
| 2017 | Bill Gates      | 86.0                    | Microsoft        |
| 2018 | Jeff Bezos      | 112.0                   | Amazon           |
| 2019 | Jeff Bezos      | 131.0                   | Amazon           |
| 2020 | Jeff Bezos      | 113.0                   | Amazon           |
| 2021 | Elon Musk       | 151.0                   | Tesla/SpaceX     |
| 2022 | Elon Musk       | 219.0                   | Tesla/SpaceX     |
| 2023 | Bernard Arnault | 211.0                   | LVMH             |
| 2024 | Bernard Arnault | 240.0                   | LVMH             |

## Visualization

The project includes a bar plot visualizing the net worth of these individuals over the specified years, distinguished by their source of wealth.


### Screenshots

![richPerson](https://github.com/user-attachments/assets/02bcb02d-f637-45f5-94b4-630061e4acff)






### Code Implementation

```python
import numpy as np
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt

# Load dataset
dataset = pd.read_csv("richest_person_2015_2024.csv")

# Create a new column combining Person and Year
dataset["Person_Year"] = dataset["Person"] + " (" + dataset["Year"].astype(str) + ")"

# Set the figure size
plt.figure(figsize=(10, 5))

# Create the bar plot
sns.barplot(x="Person_Year", y="Net Worth (Billion USD)", data=dataset, hue="Source of Wealth")

# Add titles and labels
plt.title("Net Worth of Richest Persons by Year (2015-2024)")
plt.ylabel("Net Worth (Billion USD)")
plt.xlabel("Person (Year)")
plt.xticks(rotation=45)  # Rotate x-axis labels for better readability
plt.legend(title="Source of Wealth")

# Show the plot
plt.show()


