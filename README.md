# Algorithm for QR Decomposition
## Aim:
To implement QR decomposition algorithm using the Gram-Schmidt method.
## Equipment’s required:
1.	Hardware – PCs
2.	Anaconda – Python 3.7 Installation / Moodle-Code Runner
## Algorithm:
1.	Intialize the matrix Q and u
2.	The vector u and e is given by

    ![eqn1](./ex4.jpg)

    ![eqn2](./ex6.jpg)

    ![eqn3](./ex3.jpg)

3.	Obtain the Q matrix   
    ![eqn4](./ex1.jpg)
4.	Construct the upper triangular matrix R
    ![eqn5](./ex2.jpg)



## Program:
### Gram-Schmidt Method
```
''' 
Program to QR decomposition using the Gram-Schmidt method
Developed by: VIJIYALAKSHMI A
RegisterNumber: 25017569
'''
import numpy as np
def qr_decomposition(A):
    A=np.array(A,dtype=float)
    m,n=A.shape
    Q=np.zeros((m,n))
    R=np.zeros((n,m))
    for j in range(n):
        v=A[:,j]
        for i in range(j):
            R[i,j]=np.dot(Q[:,i],A[:,j])
            v=v-R[i,j]*Q[:,i]
        R[j,j]=np.linalg.norm(v)
        Q[:,j]=v/R[j,j]
    return Q,R
A=np.array(eval(input()))
Q,R=qr_decomposition(A)
print("The Q Matrix is\n",Q)
print("The R Matrix is\n",R)

```

## Output

<img width="1234" height="376" alt="Screenshot 2025-11-27 103210" src="https://github.com/user-attachments/assets/b4a60422-855f-4531-9578-a06415708bc5" />
<img width="1183" height="547" alt="Screenshot 2025-11-27 103233" src="https://github.com/user-attachments/assets/5560cce8-d498-40ef-9d61-e78fd9b51cb4" />
<img width="1236" height="594" alt="Screenshot 2025-11-27 103251" src="https://github.com/user-attachments/assets/9d5c2362-06df-4c7f-8eac-21a0b2abffa6" />

## Result
Thus the QR decomposition algorithm using the Gram-Schmidt process is written and verified the result.
