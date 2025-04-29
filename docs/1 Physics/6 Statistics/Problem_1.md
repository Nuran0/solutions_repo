# Simulating Sampling Distributions

## Overview
In this task, we will simulate sampling distributions from various population distributions. The goal is to observe how the sampling distribution of the sample mean behaves as the sample size increases, which illustrates the Central Limit Theorem (CLT). We will work with three types of population distributions:

1. **Uniform distribution**
2. **Exponential distribution**
3. **Binomial distribution**

## Setup

The steps are as follows:

1. **Generate population data** from each distribution.
2. **Take random samples** from the population and compute the sample mean.
3. **Repeat the sampling process** many times to build the sampling distribution of the mean.
4. **Visualize the results** using histograms and probability density functions (PDFs).

## Code
![alt text](image.png)

```python
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns


# Set random seed for reproducibility
np.random.seed(42)

# Parameters
population_size = 10000
num_samples = 1000
sample_sizes = [5, 30, 100]  # Different sample sizes to observe the CLT
population_types = ['uniform', 'exponential', 'binomial']

# Function to simulate sampling distribution for a given distribution
def simulate_sampling_distribution(population_type, population_size, num_samples, sample_size):
    if population_type == 'uniform':
        population = np.random.uniform(0, 1, population_size)
    elif population_type == 'exponential':
        population = np.random.exponential(1, population_size)
    elif population_type == 'binomial':
        population = np.random.binomial(10, 0.5, population_size)
    
    sample_means = []
    
    for _ in range(num_samples):
        sample = np.random.choice(population, sample_size, replace=False)
        sample_means.append(np.mean(sample))
    
    return sample_means

# Plotting function for each distribution
def plot_sampling_distribution(population_type, population_size, num_samples, sample_sizes):
    fig, axes = plt.subplots(1, len(sample_sizes), figsize=(15, 5))
    
    for i, sample_size in enumerate(sample_sizes):
        sample_means = simulate_sampling_distribution(population_type, population_size, num_samples, sample_size)
        
        ax = axes[i]
        sns.histplot(sample_means, kde=True, ax=ax, bins=30, stat='density')
        ax.set_title(f'Sample size = {sample_size}')
        ax.set_xlabel('Sample Mean')
        ax.set_ylabel('Density')
    
    fig.suptitle(f'Sampling Distribution for {population_type.capitalize()} Distribution')
    plt.tight_layout()
    plt.subplots_adjust(top=0.85)
    plt.show()

# Simulate and plot for each population type
for population_type in population_types:
    plot_sampling_distribution(population_type, population_size, num_samples, sample_sizes)
