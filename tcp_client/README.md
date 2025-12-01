# TCP Client
There have been countless times during penetration tests that I've needed to whip up a TCP client
to test for services, send garbage data, fuzz, or any number of other tasks.
If you are working within the confines of large enterprise environments, you won't have the luxury
of networking tools or compilers, and sometimes you'll even be missing the absolute basics like
the ability to copy/paste or an Internet connection.
This is where being able to quickly create a TCP client comes in extremely handy. But enough jabbe-
ring - let's get coding. A simple TCP client in the same folder


## Explanation
We first create a socket object with the `AF_IENT` and `SOCK_STREAM` parameters.
The `AF_INET` parameters is saying we are going to use a standard IPv4 address or hostname, and
`SOCK_STREAM` indicates that this will be a TCP client. We then connect to the server and send it
some data. The last step is to receive some data back and print out the responses. This is the 
simplest form of a TCP client, but the one you will write most often.

In the given code snippet, we are making some serious assumptions about sockets that you definitely
want to be aware of. The first assumption is that our connection will always succeed, and the
the second is that the server is always expecting us to send data first (as opposed to servers that
expect to send data to you first and await your response).
Our third assumption is that the server will always send us data back in a timely fashion. We make
these assumptions largely for simplicity's sake. While programmers have varied opinions about how 
to deal with blocking sockets, exception-handling in sockets, and the like, it's quite rare for
pentesters.

