# HW4

## Question 1
*Answer 1*: 

Path from * to X
- A: D, C, Z, X
- B: A, D, C, Z, X
- C: Z, X
- D: C, Z, X
- V: W, Z, X
- W: Z, X
- Y: Z, X
- Z: X

*Answer 2*:

Path from Y to *
- A: Z, C, D, A
- B: Z, C, D, A, B
- C: Z, C
- D: Z, C, D
- V: Z, C, D, A, V
- X: Z, X
- Z: Z
    
*Answer 3*:

Path from X to *
- A: Z, C, D, A
- B: Z, C, D, A, B
- C: Z, C
- D: Z, C, D
- V: Z, C, D, A, V
- Y: Z, Y
- Z: Z

## Question 2

**default means any other conditions**

*Answer 1*: 

Match | Action
--- | ---
IP src 10.0.1.2 <br> IP src 10.3.0.5 <br> IP dest 10.2.0.3 | forward(3)
IP src 10.0.1.2 <br> IP src 10.3.0.5 <br> IP dest 10.2.0.4 | forward(4)
default | DROP

*Answer 2*: 
Match | Action
--- | ---
TCPsrcPort = * <br> TCPdestPort = * <br> IP dest 10.2.0.3 | forward(3)
TCPsrcPort = * <br> TCPdestPort = * <br> IP dest 10.2.0.4 | forward(4)
default | DROP

**\* means anything**

*Answer 3*: 
Match | Action
--- | ---
IP dest 10.2.0.4 | forward(4)
default | DROP

*Answer 4*: 
Match | Action
--- | ---
TCPsrcport = undefined <br> TCPdestport = undefined<br> IP src 10.3.0.6 <br> IP dest 10.2.0.3 | forward(3)
default | DROP

## Question 3
*Question*



*Answer*: 
   
## Question 4
*Question*



*Answer*: 


## Question 5
*Question*



*Answer*: 

## Question 6
*Question*



*Answer*: 
