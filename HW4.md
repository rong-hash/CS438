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
1.  
(a) There are nine 1 bits so the priority bit should be one. 
Need to add 1 bit.  
(b) Need to add 9 bits.     
(c) 
| | col 1| col 2| col 3| col 4| P|
|---|--|--|--|--|--|
|row 1|1|1|1|1| 0| 
|row 2|0|0|1|1| 0|
|row 3|1|0|0|0|1|
|row 4|1|0|0|1|0|
|P|1|1|0|1|  1 |

(d)

Example: 
| | col 1| col 2| col 3| col 4| P|
|---|--|--|--|--|--|
|row 1|1|1|1|1| 0| 
|row 2|0|0|1|1| 0|
|row 3|1|1|0|0|0|
|row 4|1|0|0|1|0|
|P|1|0|0|1|  0 |

Bit at row 3 col 2 flips. 
This will affect two parity bit so the parity bit for row 1 and parity bit for col 1 also flips. 
Bit at right corner also needs to flip.  


(e) 
Advantage: Most of the time, two-dimensional parity can find the location of the error bit. It's also more stable than one parity bit.     
Disadvantage: It takes more space to store parity bit. 
2.  

(a) 11110011 10001001 00000000 / 1 00100110 

|step | quotient| remainder|
|-----|---------|-------|
|(0) |  1|  011000001000100100000000 
|(1)  | 1 |   01010010000100100000000    
|(2)  | 1 |     0011011100100100000000   
|(3)  | 0 |       011011100100100000000  
|(4)  | 1 |         01001111100100000000 
|(5)  | 1 |           0000110000100000000    
|(6)  | 0 |             000110000100000000   
|(7)  | 0 |               00110000100000000  
|(8)  | 0 |                 0110000100000000 
|(9)  | 1 |                   010100010000000    
|(10)   | 1 |                     00110001000000    
|(11)   | 0 |                       0110001000000   
|(12)   | 1 |                         010101110000  
|(13)   | 1 |                           00111101000 
|(14)   | 0 |                             0111101000    
|(15)   | 1 |                               011001110   

CRC bit is 11001110. 
(b) result is 11110011 10001001 11001110. 
(c) Divide the result by 100100110. The remainder should be zero. If it's not zero, the error will be detected. 
(d) 01110011 10001001 11001110 / 1 00100110
|step | quotient| remainder|
|-----|---------|-------|
(0)   |1 | 01110100000100111001110
(1)  | 1  |  0111101100100111001110
(2)  | 1   |   011001010100111001110
(3)  |  1   |     01011001100111001110
(4)  | 1      |    0010000000111001110
(5)  | 0      |      010000000111001110
(6)  | 1        |      00010011111001110
(7)  | 0      |          0010011111001110
(8)  | 0        |          010011111001110
(9)  |1          |          00001100001110
(10)  | 0          |            0001100001110
(11)  | 0        |                001100001110
(12) |  0        |                  01100001110
Remainder is not zero and error will be detected. 
3.  
7EFF + AAC8 = 1 29C7    --> roll back: 2928 
2928 + EC05 = 1 152D    --> roll back: 152E
not(152E)  = EAD1
check sum is EAD1




## Question 5
*Question*

*Answer*: 
1. There are $2^{i-1}$ slots to choose and when A and B choose the same slot, a  collision happens. The probability is $2^{i-1} * (1/ 2^{i-1})* (1/2^{i-1}) = 1/2^{i-1}$

2. 
$p_{1} =1 - 1/2^{1-1} = 0$  
$p_{2} =(1/2^{1-1}) * (1-1/2^{2-1})  = 1/2$     
$p_{3} =(1/2^{1-1}) * (1/2^{2-1}) * (1-1/2^{3-1}) = 3/8 $
$p_{4} =(1/2^{1-1}) * (1/2^{2-1}) * (1/2^{3-1}) * (1 - 1/2^{4-1})= 7/64 $

3. 
2 collisions happen for A and 3 collisions happen for B. 
A waits for slot 0 to 3 and B waits for slot 0 to 7. 
A waits i slot and B should wait from i+1 to 7 slot.    
$P = 1/4 *(7/8+6/8+5/8+4/8) = 11/16$



## Question 6
*Question*



*Answer*:   
1. F(A)B, E(A)B, A(B)C, B(C)D
2. No. F and E can both send message to A though B at the same time and collision may occur. 
3. ACK is necessary. Packet can losy and ACK is needed to tell the sender that the node have recieved the packet. If the sender haven't recieved packet for some time, it will resend packet. 
4. 
    (a)$P_{Rx} = {G_{Tx}G_{Rx} \lambda^{2} \over (4\pi d)^{2}} * P_{Tx}$
    So, $P_{Rx}\varpropto {1 \over d^{2}}$     
    Assume the power at D is P. 
    For d = 3, $SINR = P/(P/9) = 9$    
    (b) The noise at D is P/18. 
    $SINR = P/(P/18) = 18$
5.  
(a) BPSK should be used. When SNR = 12dB, only BPSK has BER less than 
$10^{-6}$   
(b) 1 bit per second. It's 10 Mbps.     
(c) $P = 1 - (1-10^{-8})^{1500} = 0.0183$