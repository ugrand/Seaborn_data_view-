Seaborn is a popular Python visualization library based on matplotlib that provides a high-level interface for creating attractive and informative statistical graphics. To demonstrate how to use Seaborn for data visualization, we will create a few common types of plots using a sample dataset. First, make sure you have Seaborn and matplotlib installed:

bash
Copy code
pip install seaborn matplotlib
Let's use the famous Iris dataset for this demonstration, which is a classic dataset in the field of machine learning and statistics. It includes data on iris flowers with four features: sepal length, sepal width, petal length, and petal width, and it includes iris species as a categorical variable.

Here's a basic script illustrating how to create different types of plots with Seaborn:

import seaborn as sns
import matplotlib.pyplot as plt
import pandas as pd

# Load the Iris dataset
iris = sns.load_dataset('iris')

# Set the aesthetic style of the plots
sns.set_style('whitegrid')

# Histogram / Distribution Plot
plt.figure(figsize=(8, 6))
sns.histplot(iris['sepal_length'], kde=True, color='blue')
plt.title('Distribution of Sepal Length')
plt.show()

# Scatter Plot
plt.figure(figsize=(8, 6))
sns.scatterplot(data=iris, x='sepal_length', y='sepal_width', hue='species')
plt.title('Sepal Length vs Sepal Width by Species')
plt.show()

# Pair Plot
sns.pairplot(iris, hue='species')
plt.show()

# Box Plot
plt.figure(figsize=(8, 6))
sns.boxplot(x='species', y='sepal_length', data=iris)
plt.title('Box Plot of Sepal Length by Species')
plt.show()

# Heatmap (using Iris correlation matrix)
plt.figure(figsize=(8, 6))
sns.heatmap(iris.corr(), annot=True, cmap='coolwarm')
plt.title('Correlation Matrix of Iris Dataset')
plt.show()

In this script:

Histogram/Distribution Plot: Shows the distribution of sepal lengths across all iris flowers in the dataset.

Scatter Plot: Depicts the relationship between sepal length and sepal width, colored by species.

Pair Plot: Provides pairwise scatter plots and histograms for all features, differentiated by species. It's a great way to get a quick overview of relationships and distributions in a dataset.

Box Plot: Useful for visualizing the spread and skewness of data, as well as comparing different categories (in this case, species).

Heatmap: Displays the correlation matrix for the Iris dataset. It's a useful tool for understanding the relationships between different variables.

Remember, each type of plot can be customized extensively in Seaborn using various parameters to adjust the appearance and behavior of the plots to suit your specific needs. The Iris dataset used in this example is a built-in dataset in Seaborn, which makes it convenient for demonstration purposes. For your own datasets, you would load them into a Pandas DataFrame and then apply these plotting techniques in a similar way.

