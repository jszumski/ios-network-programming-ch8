# Professional iOS Network Programming
## Chapter 8: Low-Level Networking

The example code from Chapter 8 of my book, [Professional iOS Network Programming](http://www.wiley.com/WileyCDA/WileyTitle/productCd-1118362403,descCd-description.html "Professional iOS Network Programming: Connecting the Enterprise to the iPhone and iPad").  Further discussion is also available on the [Wiley P2P forum](http://p2p.wrox.com/book-professional-ios-network-programming-connecting-enterprise-iphone-ipad-708/).


The Low-Level Networking app communicates with a fake warehouse server that responds to `telnet` queries about the warehouse's current status and evironment conditions.  A segmented control in the app allows the user to switch between three modes of communication:

* BSD sockets
* CFStream
* NSStream

Each different networking type is built to read the same telnet feed, so it is easy to do an apples-to-apples comparison between all three methods.


### Warehouse Server Output

Although an example `telnet` server is not provided, the warehouse server is expected to return results in a comma-separated format:

```
84,60,+67,1,1,0,0,0,1
```

where the values mean

```
{room temperature},{outlet temperature},{coil temperature},{compressor status},{air switch status},{auxiliary heat status},{front door status},{system status},{alarm status}
```