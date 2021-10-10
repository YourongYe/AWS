
# DNS server vs IP address vs Hostname
## Definitions

Each system on a network has two unique values:
- The IP address
- The host name
 
The IP address is a computer address that lets one IP device locate another IP device and interact with it. The IP address, however, does not always uniquely identify a particular device. It is similar to your street address. While you live there, people can locate you and contact you. However, what happens when you move?
 
A computer's host name is more permanent form of identification. Even though it can be changed, it is meant to be a constant unique identifier for the computer. It is the name of the computer itself that follows the computer wherever it moves.
 
Once a computer has these two pieces of information, the DNS (Domain Name System) server ties the two together. **Think of the DNS server as a constantly updated address book.** If you use static IP addresses, the DNS server records this information. However, if you allow dynamic IP addresses, the DNS server is the network component that gives out those addresses. It knows where every system is on its network at all times. When you access a system via the host name, you actually connect to the DNS server to obtain the current IP address of that system.
 
## Recommendations
Many applications allow you to choose between using the host name and the IP address.
 
If your network uses static IP addresses and can expand without restructuring the network and reassigning IP addresses, RJS Software strongly recommends using the IP address. The IP address gives you the same connection without spending time looking up the IP address on the DNS server. While this look-up usually only takes a fraction of a second, it can occasionally take longer or even time out.
 
If your network uses dynamic IP addresses, use the host name.
