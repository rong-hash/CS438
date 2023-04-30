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
*Answer*: 

Type | MAC Src | MAC Dst | IP Src | IP Dst | TCP Src | TCP Dst | TCP Flags | Sender | Link
--- | --- | --- | --- | --- | --- | --- | --- | --- | --- | 
ARP | 0:0:0:0:0:1 | FF:FF:FF:FF:FF:FF |  10.0.0.2 | 10.0.0.1 | N/A | N/A | N/A | A | A-S
ARP | 0:0:0:0:0:1 | FF:FF:FF:FF:FF:FF |  10.0.0.2 | 10.0.0.1 | N/A | N/A | N/A | S | S-R
ARP | 0:0:0:0:0:1 | FF:FF:FF:FF:FF:FF |  10.0.0.2 | 10.0.0.1 | N/A | N/A | N/A | S | S-B
ARP | 0:0:0:0:0:3 | 0:0:0:0:0:1 |  10.0.0.1 | 10.0.0.2 | N/A | N/A | N/A | R | R-S
ARP | 0:0:0:0:0:3 | 0:0:0:0:0:1 |  10.0.0.1 | 10.0.0.2 | N/A | N/A | N/A | S | S-A
ARP | 0:0:0:0:0:4 | FF:FF:FF:FF:FF:FF |  192.168.0.1 | 192.168.0.2 | N/A | N/A | N/A | R | R-C
ARP | 0:0:0:0:0:5 | 0:0:0:0:0:4 | 192.168.0.2 | 192.168.0.1 | N/A | N/A | N/A | C | C-R
TCP | 0:0:0:0:0:1 | 0:0:0:0:0:3 | 10.0.0.2 | 192.168.0.2 | 54321 | 1234 | SYN | A | A-S
TCP | 0:0:0:0:0:1 | 0:0:0:0:0:3 | 10.0.0.2 | 192.168.0.2 | 54321 | 1234 | SYN | S | S-R
TCP | 0:0:0:0:0:4 | 0:0:0:0:0:5 | 10.0.0.2 | 192.168.0.2 | 54321 | 1234 | SYN | R | R-C
   
## Question 4
*Question*



*Answer*: 


## Question 5
*Question*



*Answer*: 

## Question 6
*Question*



*Answer*: 
