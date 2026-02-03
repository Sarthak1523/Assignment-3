Probability-Density-Functions-using-Roll-Number-Parameterized-Non-Linear-Model
1. Methodology
Data Collection → Data Pre-processing → Non-Linear Transformation →
Parameter Estimation → PDF Modeling → Result Analysis

2. Dataset Information
Dataset Name: India Air Quality Dataset
Source: Kaggle
Dataset Link: https://www.kaggle.com/datasets/shrutibhargava94/india-air-quality-data
Feature Used: NO₂ concentration
Description: The dataset contains air quality measurements collected across multiple Indian cities. The NO₂ feature is used as the input variable for learning the probability density function.
3. Input / Output
Input
Raw NO₂ values from air quality dataset
Output
Transformed variable z
Learned probability density function
Estimated parameters
Variable	Description
x	Original NO₂ value
z	Transformed value
p̂(z)	Predicted probability
4. Mathematical Formulation
Non-Linear Transformation
z=x+arsin(brx)

where
aᵣ=0.05*(r mod 7)
bᵣ=0.3*(r mod 5 + 1)

r is the university roll number.(102317012 in this case)

Probability Density Function
p(z) = cexp(−lambda(z−mu)**2)

5. Result Table
Parameter	Meaning	Value
mu	Mean of transformed data	Computed
lambda	Spread parameter	Computed
c	Normalization constant	Computed
6. Result Graph
A histogram of the transformed variable z is plotted along with the learned probability density function. The graph shows a close fit between the empirical distribution and the learned model.

7. Observations
Non-linear transformation increases data variability
Learned PDF successfully models the transformed data
Roll-number parameterization ensures uniqueness
8. Conclusion
This assignment demonstrates the application of non-linear transformations and probabilistic modeling to learn a valid probability density function from real-world air quality data.

9. Tools Used
Google Colab
Python
NumPy
Pandas
Matplotlib
10. Repository Structure
Probability-Density-Functions-using-Roll-Number-Parameterized-Non-Linear-Model │── Probability_Density_Functions.ipynb
│── README.md

