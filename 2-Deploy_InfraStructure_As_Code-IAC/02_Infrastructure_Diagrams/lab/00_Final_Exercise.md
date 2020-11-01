#Create a diagram to represent a corporate-only cloud
There is one more real-world scenario that is very popular, but not covered in this course. And that is the “extension of the on-premises network”.

In this case, you’d have a network that only contains private subnets, and does not have NAT Gateways. These components get replaced by a VGW (Virtual Gateway) and a VPN Connection. You’ll also need a CGW (Customer Gateway), which represents the on-premises side of the VPN Connection.

