## Scenario:
1. Creates VPC of your own CIDR IPv4 range.(Primary IPv4-CIDR block range /28 to /16 + 4 secondary IPv4-CIDR blocks can be attached)
2. Creates 2 Public and 2 Private Subnets spanned across different Availability Zones.(For high availability and fault tolerant incase instances get launched into this/5 Addresses are reserved per subnet block)
3. Creates 1 Internet Gateway and gets attached to VPC.(Instances in Public subnet to reach internet and vice-versa)
4. Creates 1 Public and 1 Private route table.(Table which has route to IGW is Public route table)
5. Explicit Subnet Associations with route tables.(Otherwise subnets that are not associated with any other route table tries to follow Default route table created by AWS)

## Cloudformation Concepts:
1. Parameters (Nothing but Dynamic Inputs)
2. Resources  (AWS Resources and this is the block how we declaratively tell CloudFormation to create resources)

## OtherInfo:
1. Template is re-usable in any region.
2. NACL/Security Groups/EIP/Enpoints/Endpoint Services/NAT Gateways/VPN also can be created the same way.

## Quick Info :
1. NAT Gateway lets instances in Private Subnet to reach Internet but vice-versa not possible.
2. Internet Gateway allows users from Internet to reach instances and they can response back provided proper NACL and Security Groups rules attached.
