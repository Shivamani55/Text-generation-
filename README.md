import matplotlib.pyplot as plt
import seaborn as sns
import squarify
import numpy as np
import pandas as pd

# Sample data for visualizations
data = {
    'Category': ['A', 'B', 'C', 'D', 'E'],
    'Values': [23, 45, 56, 78, 33]
}
df = pd.DataFrame(data)

# 1. Bar Chart
plt.figure(figsize=(6, 4))
plt.bar(df['Category'], df['Values'], color='skyblue')
plt.title('Bar Chart')
plt.xlabel('Category')
plt.ylabel('Values')
plt.grid(True, linestyle='--', alpha=0.5)
plt.tight_layout()
plt.show()

# 2. Heat Map
heat_data = np.random.rand(5, 5)
plt.figure(figsize=(6, 5))
sns.heatmap(heat_data, annot=True, cmap='YlGnBu')
plt.title('Heat Map')
plt.tight_layout()
plt.show()

# 3. Histogram
data_hist = np.random.normal(50, 15, 200)
plt.figure(figsize=(6, 4))
plt.hist(data_hist, bins=10, color='purple', edgecolor='black')
plt.title('Histogram')
plt.xlabel('Value Range')
plt.ylabel('Frequency')
plt.grid(True, linestyle='--', alpha=0.5)
plt.tight_layout()
plt.show()

# 4. Pie Chart
plt.figure(figsize=(6, 6))
plt.pie(df['Values'], labels=df['Category'], autopct='%1.1f%%', startangle=90, colors=plt.cm.Pastel1.colors)
plt.title('Pie Chart')
plt.tight_layout()
plt.show()

# 5. Treemap
plt.figure(figsize=(6, 4))
squarify.plot(sizes=df['Values'], label=df['Category'], color=plt.cm.Set3.colors, alpha=0.8)
plt.title('Treemap')
plt.axis('off')
plt.tight_layout()
plt.show()
