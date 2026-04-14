## 1. Create VPC
    What:Main private network in AWS.
    
    Why:Isolates your resources securely.

    When: Before creating any AWS resources.



## 2. Enable DNS Hostnames
    What:-Gives public DNS names to instances. 
    
    Why:-Easy access via hostname.
    
    When:-For public EC2 / websites.



## 3. Enable DNS Resolution
What:- Allows domain name lookup inside VPC.

Why:- Needed for internet / AWS service access.

When:- Always recommended.



## 4. Verify VPC Creation
What

Confirm VPC is active.

Why

Prevents setup issues later.

When

Right after VPC creation.

## 5. Create S3 Endpoint — vpce-0f5d29e7709c6cef7
What

Private connection to Amazon S3.

Why

Secure S3 access without internet.

When

When app needs private S3 access.

## 6. Create Public Subnet 1 — subnet-06df782840f09c5c0
What

First subnet for public resources.

Why

To host internet-facing servers.

When

For web apps.

## 7. Create Public Subnet 2 — subnet-033cb19afc22607ce
What

Second public subnet.

Why

High availability across Availability Zones.

When

For Multi-AZ setup.

## 8. Create Private Subnet 1 — subnet-051228adf9c7e3d50
What

Internal subnet for backend / DB.

Why

Provides better security.

When

For APIs / databases.

## 9. Create Private Subnet 2 — subnet-0eaf9952fb0cd23fc
What

Second private subnet.

Why

High availability.

When

For production setup.

## 10. Create Internet Gateway — igw-0cca320e9c30ee48e
What

Gateway to connect VPC to internet.

Why

Allows public access for EC2.

When

For public apps / websites.

## 11. Attach Internet Gateway to VPC
What

Connect IGW with VPC.

Why

Enables internet traffic flow.

When

After IGW creation.

## 12. Create Public Route Table — rtb-0cefbb8dab538a83f
What

Route rules for public subnet.

Why

Controls internet traffic path.

When

After subnet creation.

## 13. Create Internet Route
What

Add route:

0.0.0.0/0 → Internet Gateway
Why

Allows outbound internet access.

When

For public subnet setup.

## 14. Associate Route Table with Public Subnet 1
What

Attach route table.

Why

Apply internet route.

When

After route creation.

## 15. Associate Route Table with Public Subnet 2
What

Attach route table.

Why

Enable internet access in second subnet.

When

For high availability.

## 16. Create Private Route Table 1 — rtb-05d5b953e6c7ed3ae
What

Private subnet route rules.

Why

Secure internal traffic.

When

For backend services.

## 17. Associate Route Table with Private Subnet 1
What

Attach route table.

Why

Apply private routing.

When

After route table creation.

## 18. Create Private Route Table 2 — rtb-0aa12a0d68c2feabf
What

Route table for second private subnet.

Why

Provides isolation + HA.

When

For production setup.

## 19. Associate Route Table with Private Subnet 2
What

Link route table.

Why

Apply routing rules.

When

After creation.

## 20. Verify Route Table Setup
What

Check:

Route entries
Subnet associations
Why

Ensures traffic flows correctly.

When

After full network setup.

## 21. Associate S3 Endpoint with Private Route Tables
    What
    
    - Link S3 endpoint to private route tables.
    
    Why
    
    Private subnets can access S3 securely.
    
    When
    
    For private storage access.
