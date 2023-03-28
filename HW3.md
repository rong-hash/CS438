# HW3

## Question 1
### *Answer 1*: 

``` python
r0 = 1
a = 0.7
realrtt = 0.5
finalrtt = r0
for i in range(20):
    finalrtt = a * finalrtt + (1 - a) * realrtt
finalrtt
```
With this python simulation code, we can get the RTT-timeout(20) = 0.5004
    
### *Answer 2*: 

After changing $\alpha = 0.5$, RTT-timeout(20) = 0.5000

After changing $\alpha = 0.95$, RTT-timeout(20) = 0.679242961204271

We can find out when $\alpha$ is bigger, then the convergence is slower, when it is smaller, the convergence is faster, with the assumption that the real rtt never changes.

---
## Question 2
*Answer 2*: 


---
## Question 3
### *Answer 1*: 

For subnet A, 128 addresses suffice;

For subnet B, 32 addresses suffice;

For subnet C, 32 addresses suffice; 

So, 

A: **200.20.15.0**0000000/25 = 200.20.15.0/25

B: **200.20.15.100**00000/27 = 200.20.15.128/27

C: **200.20.15.101**00000/27 = 200.20.15.160/27

### *Answer 2*: 

128.174.240.0/20: **128.174.1111**0000.0/20, so $2^{12}$ address in total

128.174.240.128/25: **128.174.240.1**0000000/25, so $2^{7}$ addresses in total

128.174.240.17: 1 address in total

128.174.252.0/22: **128.174.111111**00.0/22, so $2^{10}$ addresses in total

128.174.240.16/29: **128.174.240.00010**000, so $2^3$ addresses in total

128.174.248.0/22: **128.174.111110**00.0/22, so $2^{10}$ addresses in total

### *Answer 3*: 

(a) R2

(b) Interface 1

(c) Interface 2

(d) Interface 3

(e) Interface 4

(f) R3

---
## Question 4
*Question*



*Answer*: 

---

## Question 5

### *Answer 1*

Step | N | D(A) | D(B) | D(C) | D(D) | D(F) | D(G)
--- | ---| ---| ---| ---| ---| ---| ---| 
0   | E | INF | INF | 6, E| 4, E|3, E | INF
1   | EF | INF | INF | 6, E | 4, E | | 5, F
2   | EFD| INF | 5, D | 6, E | | | 5, F
3   | EFDB| 17, B| | 6, E| | | 5, F
4   | EFDBG| 17, B | | 6, E| | | 
6   | EFDBGC | 14, C | | | | |
7   | EFDBGCA | | | | | |

### *Answer 2*

![IMG](img/HW3_5.png)

### *Answer 3*
**Step 1**

Node B:
_ | B | C | D
--- | --- | --- | ---|
B | 0 | 4 | 1
C | 4 | 0 | 3
D | 1 | 3 | 0

Node C:
_ | B | C | D
--- | --- | --- | ---|
B | 0 | 4 | 1
C | 4 | 0 | 30
D | 1 | 3 | 0


Node D:
_ | B | C | D
--- | --- | --- | ---|
B | 0 | 4 | 1
C | 4 | 0 | 3
D | 1 | 30 | 0

**Step 2**

Node B:
_ | B | C | D
--- | --- | --- | ---|
B | 0 | 9 | 1
C | 4 | 0 | 30
D | 1 | 30 | 0

Node C:
_ | B | C | D
--- | --- | --- | ---|
B | 0 | 4 | 1
C | 4 | 0 | 5
D | 1 | 30 | 0


Node D:
_ | B | C | D
--- | --- | --- | ---|
B | 0 | 4 | 1
C | 4 | 0 | 30
D | 1 | 5 | 0

**Step 3**

Node B:
_ | B | C | D
--- | --- | --- | ---|
B | 0 | 6 | 1
C | 4 | 0 | 5
D | 1 | 5 | 0

Node C:
_ | B | C | D
--- | --- | --- | ---|
B | 0 | 9 | 1
C | 6 | 0 | 5
D | 1 | 5 | 0


Node D:
_ | B | C | D
--- | --- | --- | ---|
B | 0 | 9 | 1
C | 4 | 0 | 5
D | 1 | 5 | 0

**Step 4**

Node B:
_ | B | C | D
--- | --- | --- | ---|
B | 0 | 6 | 1
C | 6 | 0 | 5
D | 1 | 5 | 0

Node C:
_ | B | C | D
--- | --- | --- | ---|
B | 0 | 9 | 1
C | 6 | 0 | 5
D | 1 | 5 | 0


Node D:
_ | B | C | D
--- | --- | --- | ---|
B | 0 | 9 | 1
C | 4 | 0 | 5
D | 1 | 5 | 0

...

**Step N**:

Node B:
_ | B | C | D
--- | --- | --- | ---|
B | 0 | 9 | 1
C | 9 | 0 | 10
D | 1 | 10 | 0


Node D:
_ | B | C | D
--- | --- | --- | ---|
B | 0 | 9 | 1
C | 9 | 0 | 10
D | 1 | 10 | 0


---
## Question 6
### *Answer*: 



