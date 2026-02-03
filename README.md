📘 Assignment-1: Learning Probability Density Functions using a Roll-Number-Parameterized Non-Linear Model
1. Introduction

This project focuses on learning a probability density function (PDF) from real-world air quality data.
The NO₂ (Nitrogen Dioxide) concentration is used as the input feature, which is first transformed using a non-linear transformation dependent on the university roll number.
After transformation, a Gaussian-like probability density function is learned by estimating its parameters.

The dataset used is the India Air Quality Dataset from Kaggle 

Assignment-1

.

2. Dataset Description

Source: Kaggle – India Air Quality Data

Feature Used: NO₂ concentration

Variable Notation:

x → Original NO₂ value

z → Transformed value of NO₂

Before processing, missing or invalid NO₂ values are removed to ensure data quality.

3. Methodology
Step 1: Non-Linear Transformation

Each NO₂ value x is transformed into z using the following equation:

𝑧
=
𝑥
+
𝑎
𝑟
⋅
arcsin
⁡
(
𝑏
𝑟
⋅
𝑥
)
z=x+a
r
	​

⋅arcsin(b
r
	​

⋅x)

Where:

𝑎
𝑟
=
0.05
×
(
𝑟
 
m
o
d
 
7
)
a
r
	​

=0.05×(rmod7)

𝑏
𝑟
=
0.3
×
(
𝑟
 
m
o
d
 
5
+
1
)
b
r
	​

=0.3×(rmod5+1)

r is the university roll number

This transformation introduces non-linearity, making the distribution of the data more complex and realistic.

Step 2: Probability Density Function Modeling

After transformation, the probability distribution of z is modeled using:

𝑝
^
(
𝑧
)
=
𝑐
⋅
𝑒
−
𝜆
(
𝑧
−
𝜇
)
2
p
^
	​

(z)=c⋅e
−λ(z−μ)
2

Where:

μ → Mean of transformed data

λ → Controls spread (similar to inverse variance)

c → Normalization constant

Step 3: Parameter Estimation

The parameters μ, λ, and c are learned using statistical estimation techniques:

μ (Mean):
Calculated as the average of all transformed values z.

λ (Spread parameter):
Estimated using the variance of z.

c (Scaling constant):
Computed to ensure the PDF integrates to 1.

These parameters define the learned probability density function.

4. Results
4.1 Learned Parameters Table
Parameter	Description	Estimated Value
μ	Mean of transformed data	μ̂
λ	Spread control parameter	λ̂
c	Normalization constant	ĉ

(Actual values depend on the roll number and dataset subset used.)

4.2 Result Graphs
1️⃣ Histogram of Transformed Data (z)

Displays the frequency distribution of transformed NO₂ values.

Helps visualize the shape and spread of the data.

2️⃣ Learned Probability Density Function

The estimated PDF curve is plotted over the histogram.

Shows how well the learned function fits the transformed data.

📌 Observation:
The PDF closely follows the histogram shape, indicating that the estimated parameters effectively capture the underlying data distribution.

5. Discussion

The roll-number-based transformation ensures unique data behavior for each student.

The learned PDF successfully models the transformed NO₂ distribution.

Minor deviations may occur due to data skewness or environmental noise.

6. Conclusion

In this assignment, a non-linear transformation was applied to air quality data, followed by probabilistic modeling using a Gaussian-like PDF.
The parameters were successfully estimated, and the resulting probability distribution accurately represents the transformed data.

This approach demonstrates the practical application of probability density estimation on real-world datasets.
