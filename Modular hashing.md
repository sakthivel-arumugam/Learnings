https://medium.com/@nynptel/what-is-modular-hashing-9c1fbbb3c611

The method of taking the modulo of the hash to assign servers is called modular hashing. It is a simple and efficient way to distribute data or requests across a set of servers.

For example, let’s say we have 5 servers and we want to use modular hashing to assign them to 100 pieces of data. We would first use a hash function to generate a unique value for each piece of data. These values could be anything, but they would all be different.

We would then take the modulo of each value by 5. This would give us a remainder between 0 and 4. The remainder would then be used to determine which server the data should be sent to. For example, if the remainder of a piece of data is 2, then it would be sent to the second server.

However, it is important to note that modular hashing is not a perfect solution. It can lead to uneven distribution of data or requests, especially if the number of servers is small.

Here are some of the advantages of modular hashing:

It is simple to implement.
It is efficient.
It can be used with any hash function.
Here are some of the disadvantages of modular hashing:

It can lead to uneven distribution of data or requests.
It is not as fault-tolerant as other methods, such as consistent hashing.
