# Dynamic Time Warping

It is the cost of an **optimal alignment** between the measurements of two time series, $x \& x'$. Individual time points are compared by a [[Distance Functions]]

We can calculate reccursively:
![[Pasted image 20220212174947.png]]
$DTW(0,0) = 0, DTW(i,0) = \infty , DTW(0,j) = \infty \space \forall 1 \leq i \leq d, \space 1 \leq j \leq d'$


![[Pasted image 20220212173712.png]]
![[Pasted image 20220212173816.png]]![[Pasted image 20220212175443.png]]