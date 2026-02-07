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
Developed by: Aniruth S
RegisterNumber: 212225040020
'''
import numpy as np
def QR_Decomposition(A):
    A=np.array(A,dtype=float)
    m,n=A.shape
    
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
A = np.array(eval(input()))
Q,R=QR_Decomposition(A)

print("The Q Matrix is\n",Q)
print("The R Matrix is\n",R)
```

## Output

<img width="1401" height="718" alt="{788EFA37-1248-4326-B92D-66B8E68FAF00}" src="https://github.com/user-attachments/assets/75a57b12-aaba-4ad8-9c6f-08c5bb866d40" />
<img width="1446" height="435" alt="{C7E9EE52-37E7-4CB7-B3D8-8A3AEFE665E3}" src="https://github.com/user-attachments/assets/992289fd-2fa6-4be8-8711-222f3dab8c77" />
<img width="1298" height="710" alt="{E15F74F3-6585-49F5-9C31-E5BBA6D67F65}" src="https://github.com/user-attachments/assets/bceddd47-15d9-4b8e-b90b-2a1cef48d05e" />



## Result
Thus the QR decomposition algorithm using the Gram-Schmidt process is written and verified the result.
