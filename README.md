NAME:NIYOMUGABO Nice Kevin
ID: 26708
Course: Introduction to Big data
📘 Project Overview
This project analyzes the impact of sustainable fisheries on Tanzania's GDP using big data analytics techniques. The study examines trends in sustainable fisheries as a percentage share of GDP from 2014 to 2022, providing insights into the economic significance of sustainable fishing practices in Tanzania's economy.

📊 Dataset Information
Data Source: Tanzania Revenue Authority, Ministry of Livestock and Fisheries
Time Period: 2014-2022
Indicator: Sustainable fisheries as percentage share of GDP
Target: 14.7% (UN SDG 14.7.1)
Unit: Percentage
Region: Mainland Tanzania

🛠️ Technologies Used
Programming & Analysis

Python 3.x - Primary programming language
Pandas - Data manipulation and analysis
Matplotlib - Data visualization
Google Colab - Development environment

Data Processing

Excel/XLSX - Original data format
CSV - Processed data format
Tools

Jupyter Notebooks - Interactive development
Git/GitHub - Version control
Power BI - Dashboard creation 
📁 Project Structure
import pandas as pd
import matplotlib.pyplot as plt

# Step 1: Data Loading
# Create a DataFrame from the provided data
data = {
    'goal': [14] * 9,
    'target': ['14.7'] * 9,
    'indicator': ['14.7.1'] * 9,
    'description': ['Sustainable fisheries as a percentage share of GDP in Tanzania'] * 9,
    'data_sources': ['AdminisTanzania Revene Authoritytive data, Ministry of Livestock and Fisheries'] * 9,
    'year': [2014, 2015, 2016, 2017, 2018, 2019, 2020, 2021, 2022],
    'unit': ['Percentage'] * 9,
    'value': [1.8, 4.5, 1.2, 8.4, 9.2, 1.5, 6.7, 2.6, 1.9],
    'region': ['Mainland'] * 9
}

df = pd.DataFrame(data)

# Step 2: Data Cleaning
# Correct the typo in data_sources
df['data_sources'] = 'Administrative data, Tanzania Revenue Authority, Ministry of Livestock and Fisheries'

# Convert year to datetime format
df['year'] = pd.to_datetime(df['year'], format='%Y').dt.year

# Step 3: Basic Data Analysis
# Calculate key statistics
stats = {
    "Mean": df['value'].mean(),
    "Median": df['value'].median(),
    "Max Year": df.loc[df['value'].idxmax(), 'year'],
    "Min Year": df.loc[df['value'].idxmin(), 'year'],
    "Value Range": f"{df['value'].min()} - {df['value'].max()}%"
}

# Step 4: Time Series Visualization
plt.figure(figsize=(10, 6))
plt.plot(df['year'], df['value'], marker='o', linestyle='-', color='b')
plt.title('Tanzania Sustainable Fisheries GDP Share (2014-2022)', fontsize=14)
plt.xlabel('Year', fontsize=12)
plt.ylabel('Percentage of GDP', fontsize=12)
plt.grid(True, linestyle='--', alpha=0.7)
plt.xticks(df['year'])
plt.ylim(0, 10)

# Annotate values on the plot
for x, y in zip(df['year'], df['value']):
    plt.annotate(f'{y}%', (x, y), textcoords="offset points",
                 xytext=(0,10), ha='center')

plt.tight_layout()

# Step 5: Output Results
print("="*50)
print("Basic Statistics:")
for k, v in stats.items():
    print(f"{k}: {v}")

print("\nYearly Data:")
print(df[['year', 'value']].to_string(index=False))

# Save visualization
plt.savefig('tanzania_fisheries_gdp_trend.png', dpi=300)
plt.show()

OUT PUT
<img width="725" height="263" alt="photo 4" src="https://github.com/user-attachments/assets/650160d8-e3ec-4a1b-9d6f-29278ca1e41f" />
<img width="595" height="314" alt="photo 5" src="https://github.com/user-attachments/assets/538acf44-f99a-4a45-a839-54f52d377419" />

📞 Contact & Support
Author: [Niyomugabo Nice Kevin]
Email: [nicekevinniyomugabo@gmail.com]
contact: 0791369434

📚 References

United Nations. (2015). Sustainable Development Goal 14: Life Below Water
Tanzania Revenue Authority. (2023). Administrative Data Collections
Ministry of Livestock and Fisheries, Tanzania. (2022). Fisheries Development Reports
World Bank. (2023). Tanzania Economic Overview

Last Updated: August 2025
Version: 1.0.0
Status: Active Development

This project demonstrates the application of big data analytics techniques to real-world environmental and economic challenges, contributing to evidence-based policy making in sustainable fisheries management.








