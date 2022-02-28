## Second Homework

### Chapter 1: Problem 2

+ Problem:

    Equation 1.1 gives a formula for the end-to-end delay of sending one packet of length *L* over *N* links of transmission rate *R*. Generalize this formula for sending *P* such packets back-to-back over the *N* links.

+ Answer:


$$
d_{P-end-to-end} = (N)\times\frac{L}{R}+(p-1)\times\frac{L}{R} \\
d_{P-end-to-end} = (N+P-1)\times\frac{L}{R}\\
$$

+ The end-to-end delay of one  packet form  is (N*L/R), because a  packet need to be transmitted N times

+ And we know the different packets could be transmitted by different routers at the same

+ When the fist packet is transmitted by second node, the second packets is transmitted by first node at the same time

+ The whole sending process is end until the last packet arrive at the destination

+ So, the  formula for sending *P* such packets back-to-back over the *N* links is:
    $$
    d_{P-end-to-end} = (N+P-1)\times\frac{L}{R}
    $$
    



### Chapter 1: Problem 7

+ Problem:

    In this problem, we consider sending real-time voice from Host A to Host B over a packet-switched network (VoIP). Host A converts analog voice to a digital 64 kbps bit stream on the fly. Host A then groups the bits into 56-byte packets. There is one link between Hosts A and B; its transmission rate is 10 Mbps and its propagation delay is 10 msec. As soon as Host A gathers a packet, it sends it to Host B. As soon as Host B receives an entire packet, it converts the packet’s bits to an analog signal. How much time elapses from the time a bit is created (from the original analog signal at Host A) until the bit is decoded (as part of the analog signal at Host B)?

+ Answer:

    + The time of generating a packet at Host A: (56 * 8 bit) / 64 kbps = 7 msec
    + transmission delay: (56 * 8 bit) / 10 Mbps = 0.0448 msec
    + propagation delay: 10 msec
    + The totol time: 7 msec + 0.00448 msec +10 msec = 17.0448 msec

### Chapter 1: Problem 9

+ Problem:

    Consider the discussion in Section 1.3 of packet switching versus circuit switching in which an example is provided with a 1 Mbps link. Users are generating data at a rate of 100 kbps when busy, but are busy generating data only with probability *p* = 0.1. Suppose that the 1 Mbps link is replaced by a 1 Gbps link.

    a. What is *N,* the maximum number of users that can be supported simulta neously under circuit switching?

    b. Now consider packet switching and a user population of *M* users. Give a formula (in terms of *p*, *M*, *N*) for the probability that more than *N* users are sending data.

+ Answer:

    + a. 1Gbps / 100kbps = 10000 users

    + b. probability that more than *N* users are sending data:
        $$
        sum_{k=N+1}^M \tbinom{M}{N}p^k(1-p)^{M-k}
        $$