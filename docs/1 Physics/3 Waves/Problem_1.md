# PROBLEM 1


![alt text](image-5.png)

Explanation of the Code:
Constants:

Amplitude 
𝐴
A, Wavelength 
𝜆
λ, Wave number 
𝑘
k, Angular frequency 
𝜔
ω, and Phase constant 
𝜙
ϕ are all set at the beginning.

The source location is set at 
(
𝑥
0
,
𝑦
0
)
(x 
0
​
 ,y 
0
​
 ), and the frequency is 
𝑓
=
1
f=1 Hz.

Grid Creation:

We create a grid of points on the water surface using np.meshgrid to calculate the displacement 
𝜂
(
𝑥
,
𝑦
,
𝑡
)
η(x,y,t) at each grid point.

Wave Displacement Calculation:

The displacement 
𝜂
(
𝑥
,
𝑦
,
𝑡
)
η(x,y,t) at each point is calculated using the formula:

𝜂
(
𝑥
,
𝑦
,
𝑡
)
=
𝐴
𝑟
⋅
cos
⁡
(
𝑘
𝑟
−
𝜔
𝑡
+
𝜙
)
η(x,y,t)= 
r
​
 
A
​
 ⋅cos(kr−ωt+ϕ)
Where 
𝑟
r is the distance from the source to each point.

Plotting:

The contour plot visually represents the wave displacement, where the color map indicates the displacement values, with brighter areas corresponding to larger displacements (crests) and darker areas corresponding to smaller displacements (troughs).