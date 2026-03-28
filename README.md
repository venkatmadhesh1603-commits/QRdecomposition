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




Program to QR decomposition using the Gram-Schmidt method
Developed by: Madhesh V
RegisterNumber: 21225040214
```
import numpy as np
def QR_Decomposition(A):
    A=np.array(A,dtype="float")
    m,n = A.shape
    Q=np.zeros((m,n))
    R=np.zeros((n,n))
    
    for j in range(n):
        v=A[:,j]
        for i in range(j):
            R[i,j]=np.dot(Q[:,i],A[:,j])
            v=v-R[i,j]*Q[:,i]
            
        R[j,j]=np.linalg.norm(v)
        Q[:,j]=v/R[j,j]
    return Q,R
            
a = np.array(eval(input()))
Q,R=QR_Decomposition(a)
print("The Q Matrix is\n",Q)
print("The R Matrix is\n",R)

```
<img width="1233" height="870" alt="image" src="https://github.com/user-attachments/assets/155aaef8-abe6-4a5c-8cda-5a63c997df0f" />


## Output

<img width="1196" height="596" alt="519520258-36e50ed6-0cb9-4428-9c4d-d9e0130489fb" src="https://github.com/user-attachments/assets/2bcad020-136e-482b-9b76-d40a04c990b7" />



## Result
Thus the QR decomposition algorithm using the Gram-Schmidt process is written and verified the result.
