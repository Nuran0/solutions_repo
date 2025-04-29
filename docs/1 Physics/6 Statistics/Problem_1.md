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


![alt text](image.png)



# TASK 2
# Sampling and Visualization

## Overview
In this task, we will randomly sample data from a population and calculate the sample mean for different sample sizes (e.g., 5, 10, 30, 50). By repeating this process many times, we will create a sampling distribution of the sample mean. We will then plot histograms of the sample means for each sample size to observe how the distribution of the sample mean converges to a normal distribution as the sample size increases, demonstrating the Central Limit Theorem (CLT).

## Steps

1. **Sample Data**: Randomly sample from the population for different sample sizes.
2. **Calculate Sample Mean**: For each sample, calculate the mean.
3. **Repeat the Process**: Repeat the sampling process multiple times to build the sampling distribution.
4. **Visualization**: Plot histograms for each sample size and observe the convergence to normality.



![alt text](image-1.png)

# TASK 3
# Parameter Exploration

## Overview
In this task, we will explore how the shape of the original population distribution and the sample size influence the rate of convergence to normality. We will also investigate the impact of the population’s variance on the spread of the sampling distribution. The goal is to observe how different population distributions (with varying shapes) and sample sizes affect the sampling distribution of the sample mean.

### Key Concepts to Explore:
1. **Shape of the original distribution**: We will use three different population distributions—Uniform, Exponential, and Binomial—to explore how their shapes influence the rate at which the sampling distribution converges to normality.
2. **Sample size**: We will analyze how the sample size influences the rate of convergence to a normal distribution.
3. **Population variance**: The variance of the population will influence the spread of the sampling distribution of the sample mean. Larger variances lead to wider distributions for the sample means.

## Code

```python
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns

# Set random seed for reproducibility
np.random.seed(42)

# Parameters
population_size = 10000
num_samples = 1000
sample_sizes = [5, 10, 30, 50]  # Different sample sizes to observe the CLT
population_types = ['uniform', 'exponential', 'binomial']

# Function to simulate sampling distribution for a given population and sample size
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

# Plotting function for different population distributions and sample sizes
def plot_parameter_exploration(population_types, population_size, num_samples, sample_sizes):
    fig, axes = plt.subplots(len(population_types), len(sample_sizes), figsize=(15, 10))
    
    for i, population_type in enumerate(population_types):
        for j, sample_size in enumerate(sample_sizes):
            sample_means = simulate_sampling_distribution(population_type, population_size, num_samples, sample_size)
            
            ax = axes[i, j]
            sns.histplot(sample_means, kde=True, ax=ax, bins=30, stat='density')
            ax.set_title(f'{population_type.capitalize()} | Sample size = {sample_size}')
            ax.set_xlabel('Sample Mean')
            ax.set_ylabel('Density')
    
    fig.suptitle('Impact of Population Distribution, Sample Size, and Variance on Sampling Distribution')
    plt.tight_layout()
    plt.subplots_adjust(top=0.9)
    plt.show()

# Simulate and plot for different population distributions and sample sizes
plot_parameter_exploration(population_types, population_size, num_samples, sample_sizes)
