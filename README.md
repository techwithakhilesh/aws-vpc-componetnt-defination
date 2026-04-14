#  VPC and its components definition and how to setup VPC 


## 1. Create VPC
    Main private network in AWS.
        
    Isolates your resources securely.
    
     Before creating any AWS resources.



## 2. Enable DNS Hostnames
    Gives public DNS names to instances. 
        
    Easy access via hostname.
        
    For public EC2 / websites.



## 3. Enable DNS Resolution
     Allows domain name lookup inside VPC.
    
     Needed for internet / AWS service access.
    
     Always recommended.



## 4. Verify VPC Creation
     Confirm VPC is active.
    
     Prevents setup issues later.
    
     Right after VPC creation.


## 5. Create S3 Endpoint — vpce-0f5d29e7709c6cef7
    Private connection to Amazon S3.
    
    Secure S3 access without internet.
    
    When app needs private S3 access.



## 6. Create Public Subnet 1
    First subnet for public resources.
    
    To host internet-facing servers.
    
    For web apps.



## 7. Create Public Subnet 2
     Second public subnet.
    
     High availability across Availability Zones.
    
     For Multi-AZ setup.



## 8. Create Private Subnet 1
    Internal subnet for backend / DB.
    
    Provides better security.
    
     For APIs / databases.



## 9. Create Private Subnet 2 
    Second private subnet.
    
    High Availability
    
    For production setup.



## 10. Create Internet Gateway — igw-0cca320e9c30ee48e
     Gateway to connect VPC to internet.
    
     Allows public access for EC2.
    
     For public apps / websites.



## 11. Attach Internet Gateway to VPC
    Connect IGW with VPC.
    
    Enables internet traffic flow.
    
    After IGW creation.



## 12. Create Public Route Table — rtb-0cefbb8dab538a83f
    Route rules for public subnet.
    
    Controls internet traffic path.
    
    After subnet creation.



## 13. Create Internet Route

     Add  route:0.0.0.0/0 → Internet Gateway
    
    Allows outbound internet access.
    
    For public subnet setup.



## 14. Associate Route Table with Public Subnet 1
    Attach route table.
    
    Apply internet route.
    
    After route creation. 



## 15. Associate Route Table with Public Subnet 2
     Attach route table.
    
     Enable internet access in second subnet.
    
     For high availability.



## 16. Create Private Route Table 1 — rtb-05d5b953e6c7ed3ae
    Private subnet route rules.
    
    Secure internal traffic.
    
    For backend services.


## 17. Associate Route Table with Private Subnet 1
     Attach route table.
    
     Apply private routing.
    
     After route table creation.

## 18. Create Private Route Table 2 — rtb-0aa12a0d68c2feabf
    Route table for second private subnet.
    
    Provides isolation + HA.
    
    For production setup.



## 19. Associate Route Table with Private Subnet 2
     Link route table.
    
     Apply routing rules.
    
     After creation.


## 20. Verify Route Table Setup


    Check Route entries Subnet associations
    
    
    Ensures traffic flows correctly.
    
    
    After full network setup.



## 21. Associate S3 Endpoint with Private Route Tables
    Link S3 endpoint to private route tables.
        
    Private subnets can access S3 securely.
        
    For private storage access.
    

