# HW1
<br>

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

BitTorrent employs a choking mechanism for distributing bandwidth to peers. It selects the
four peers that have provided the best download performance using a tit-for-tat strategy
and one additional peer chosen randomly, referred to as an "optimistic unchoking". The
selection of the four best peers and the random choice are updated every second.

Suppose Bob joins a BitTorrent swarm with 30 other peers. Let each peer, including Bob,
have an upload speed of 80 Mbps and unlimited download speed. Consider what happens in
the phase of the protocol where for each pair of peers A and B, A has some blocks that B
wants and vice versa; i.e, any peer can productively download data from any other peer.

1. If Bob intends to not upload any data and become a free rider, what would his average
download speed be?
2. What would be the average download rate for the remaining peers?
3. Suppose that Bob runs a second client that pretends to be a separate peer, who also
becomes a free rider. How fast can Bob download data now?
4. Suppose Bob switches his two clients to the regular BitTorrent code and they both start
uploading as well. Will Bob’s performance see a noticeable improvement compared to
when he was not contributing?



*Answer*: 

1. Because Bob don't upload files so he can't be the top 4 contributor for other peers, he can only download the file when "optimistic unchoking". For each of 30 peers, Bob has only 1/ (30 -4) possibility to get connected.

    Download Speed = 80 / 5 / 26 * 30 = 18.46 Mbps

2. AvgRate = (80Mbps * 30 - 18.46Mbps) / 30 = 79.38 Mbps
3. Download Speed = 80 / 5 / 27 * 30 * 2 = 35.56 Mbps
4. Yes, he will. Current Avg Speed = 80 Mbps * 2 = 160 Mbps

## Question 4
*Question*



*Answer*: 


## Question 5
*Question*
1. How does a web server handle multiple HTTP connections at the same time, even
though all of the data packets received from different sessions are all directed to its
TCP port 80? In other words, how does the server ensure that each packet is correctly
delivered to its corresponding socket?
2. Is there a restriction on the number of simultaneous connections a single host can make
with a web server, such as "a host can only maintain one HTTP connection with the
server at any given time"? If such limitations exist, please describe them. If not, please
explain the reasons why there are no limitations.



*Answer*: 

1. When a web server receives multiple HTTP connections, it first create a specific process and then assigns a unique socket to each connection, even if all of them are directed to port 80. Each socket is associated with a unique combination of IP address and port number. The server uses this information to route incoming packets to the correct socket. The server keeps track of the state of each connection and associated sockets and uses mechanisms such as threading or asynchronous I/O to manage multiple sockets in parallel. TCP guarantees reliable and ordered delivery of packets, while HTTP uses request and response headers to ensure that packets are properly labeled and that responses are matched to the corresponding requests.

2. No. Because a host can have many applications running on several different ports. All of them can request from the same server. 



## Question 6
*Question*



*Answer*: 

## Question 1
*Question*



*Answer*: 