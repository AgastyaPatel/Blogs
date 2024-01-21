---
title: Matplotlib
author: Agastya Patel
date: 2024-01-20
date-modified: today
categories:
  - Reference
---
```py
import matplotlib.pyplot as plt

plt.figure(figsize = (10,6)) //Aspect ratio of the plot
plt.suptitle('Super Title)
plt.set_tile('Title', loc='left)
plt.xlabel('X Label')
plt.ylabel('Y Label')

# Create scatter points
plt.scatter(y_test, predictions, label='Predictions', alpha=0.5, color='blue')
# Plot a line
plt.plot([min(y_test), max(y_test)], [min(y_test), max(y_test)], linestyle='--', color='gray', linewidth=2, label="Actual Observations")

plt.legend()  # Places legend on the plot
plt.show()
```