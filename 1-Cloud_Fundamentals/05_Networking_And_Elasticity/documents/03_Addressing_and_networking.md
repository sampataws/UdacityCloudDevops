##Q) Addresses Available?
How many individual addresses are there on a /22 network (recall that several of them are reserved).
##Ans) 
2^22 -3 = 1021

#Review of Binary Conversion and the AND operator
If you watched that video and wondered, "How do I convert to binary?" and "What's an AND operation?", don't worry because the following resources will explain the basics to you.

If you'd like to learn how to convert decimal to binary by hand, read [this tutorial on the subject](https://www.electronics-tutorials.ws/binary/bin_2.html).

Once you understand how the math works and have practiced a conversion or two, you'll probably want to use an online conversion tool for efficiency's sake. The following two tools were used to perform the conversions seen in the video,

* [IP Address to Binary](https://www.browserling.com/tools/ip-to-bin)
* [Binary to IP Address](https://www.browserling.com/tools/bin-to-ip)
Additionally, the process of determining the network address given an address of a host on the network and the subnet mask requires you to perform a logical AND operation. The AND operator compares two inputs to produce an output. In the case of the address and mask, it compared each bit position individually.

The following truth table summarizes which inputs produce what output.

| Input 1 | Input 2 | Output |
|---------|---------|--------|
| 0       | 0       | 0      |
| 0       | 1       | 0      |
| 1       | 0       | 0      |
| 1       | 1       | 1      |

Happy Converting!


##Reserved Addresses on a Netblock
If you recall, the number of addresses that are available for use in a netblock were reduced by three, because those three addresses are reserved for something. Well, what are they?

* The first address (.0) is used for identification of the network,
* the follow address (.1) is often assigned to the router,
* the last address (.255) is called the broadcast address. Anything sent to the broadcast address will be sent out to all devices on the network.


##Additional Resources
Some basic reading on subnetworks and Classless Inter-Domain Routing (CIDR):

* [Subnetworks](https://en.wikipedia.org/wiki/Subnetwork),
* A good read on [CIDR](https://en.wikipedia.org/wiki/Classless_Inter-Domain_Routing) with a helpful table on all IPv4 CIDR blocks.

And several technical reports on the following subjects:

* [RFC IPv4](https://tools.ietf.org/html/rfc1878),
* [RFC IPv6](https://tools.ietf.org/html/rfc5942),
* [RFC CIDR](https://www.rfc-editor.org/rfc/rfc1519.txt).