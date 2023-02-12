# HW1

## Question 1
*Question*

The task requires using the dig command to provide answers. To ensure accurate results, it
is recommended to perform these steps from a computer located on a campus network. The
user can refer to the dig documentation to understand how to utilize it.

1. Starting from one of the root servers a–m.root-servers.net, perform an iterative lookup for the host www.eecs.mit.edu. For instance, you can initiate the search by using the following command:
    ```
    dig @h.root-servers.net www.eecs.mit.edu
    ```
    Please provide a list of the following information for each name server you visit during the lookup process:
    - Can you specify the domain name of the name server being visited?
    - Can you provide the IP address of the name server that is currently being used?
    - How long did the query take?
    - What is the round-trip time (RTT) to the server, which can be determined by using the "ping" command to connect to the server?
    - For how long can you store the results in cache?

2. Perform a *recursive* query using `resolver.illinois.edu` of the name
`www.eecs.mit.edu`. Was this query faster or slower than the sum of the iterative steps? Why do you think that is?

3. Perform an iterative reverse-mapping query for the address of `www.eecs.mit.edu` you found in the previous steps, using `dig -x`. List again the information asked in part 1.

4. Can you explain why the DNS protocol tends to utilize UDP rather than TCP, considering what has been previously discussed in this inquiry?



*Answer*: 
1.  - eecs.mit.edu
    - 35.231.163.5
    - 91 msec
    - rtt min/avg/max/mdev = 31.128/37.290/48.335/5.604 ms
    - The same time as RTT, 37.290ms (avg)
2. The recursive query would probably be quicker than completing each iterative step individually because the resolver would take care of everything for you, including issuing the required DNS queries, monitoring referral answers, and returning the final result. This can lead to fewer network round-trips, quicker response times, and a reduction in the amount of work.

3.  - eecs.mit.edu
    - 35.231.163.5
    - 27 msec
    - rtt min/avg/max/mdev = 35.024/49.701/102.223/20.766 ms
    - The same time as RTT, 49.701ms (avg)

4.  Speed: Compared to TCP, UDP is a quicker and easier protocol. UDP is an excellent fit for the DNS use case because DNS inquiries are frequently brief and only call for one request and one response.

    Stateless: Each DNS query is independent of every other query since the protocol is stateless. Because UDP does not require the overhead of establishing and maintaining a connection, it is well suited for stateless protocols like DNS.

    Error handling: The DNS protocol is designed to handle errors at the application layer, rather than relying on the underlying transport protocol to handle them. UDP is an unreliable protocol that does not guarantee delivery, but it provides faster response times and reduces overhead compared to TCP.

    Firewall traversal: UDP is frequently easier to pass through firewalls than TCP, which may make it simpler for DNS queries to reach their intended destination.

 
    

## Question 2
*Question*



*Answer*: 

    
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

## Question 1
*Question*



*Answer*: 