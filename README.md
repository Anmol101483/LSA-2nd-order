Name-harshad
Roll No-SEL69
Date-20/02/2025

Program for LSA 2nd Order
@author: harshad
"""

"Program for LSA 2nd Order"

import numpy as np
import sympy as sp

n=int(input("Enter the no. of observation\t"))

x=np.array([0 for i in range(n)])
y=np.array([0 for i in range(n)])

i=0
while (i<n):
    print("Enter the value of x%d"%i)
    x[i]=float(input())
    print("Enter the value of y%d"%i)
    y[i]=float(input())
    i=i+1
    
x2=x*x
x3=x**3
x4=x**4
xy=x*y
x2y=x2*y

Sx=np.sum(x)
Sy=np.sum(y)
Sx2=np.sum(x2)
Sx3=np.sum(x3)
Sx4=np.sum(x4)
Sxy=np.sum(xy)
Sx2y=np.sum(x2y)

a=sp.symbols('a')
b=sp.symbols('b')
c=sp.symbols('c')

eq1=sp.Eq(n*a+b*Sx+c*Sx2,Sy)
eq2=sp.Eq(a*Sx+b*Sx2+c*Sx3,Sxy)
eq3=sp.Eq(a*Sx2+b*Sx3+c*Sx4,Sx2y)

sol=sp.solve((eq1,eq2,eq3),(a,b,c))

print("The value of coefficients are",sol)

Output
Enter the no. of observation	6
Enter the value of x0
0
Enter the value of y0
0
Enter the value of x1
2
Enter the value of y1
33
Enter the value of x2
4
Enter the value of y2
55
Enter the value of x3
6
Enter the value of y3
70
Enter the value of x4
8
Enter the value of y4
80
Enter the value of x5
10
Enter the value of y5
85
The value of coefficients are {a: 8/7, b: 2337/140, c: -47/56}
