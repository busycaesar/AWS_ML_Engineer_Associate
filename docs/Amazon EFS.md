## Introduction
- Managed EFS can be mounted on many EC2.
- EFS works with EC2 instances in multi-AZ.
- Highly available, scalable, expensive, pay per use.

![EFS](efs.png)

- Use Cases: Content Management, Web Serving, Data Sharing, etc.
- Uses NFSv4.1 protocol.
- Uses security group to control access to EFS.
- Compatible with Linux based AMI (not Windows)
- Encryption at rest using KMS.
- Scales automatically, pay-per-use, no capacity planning.
## Storage Classes
### Storage Tiers
- **Standard**: For frequently accessed files.
- **Infrequent Access (EFS-IA)**: Cost to retrieve files, lower price to store.
- **Archive**: Rarely accessed data, 50% cheaper.

- Implement lifecycle policies to move files between storage tiers.
### Availability and Durability
- **Standard**: Multi-AZ. great for production
- **One Zone**: One AZ, great for dev, backup, compatible with IA (EFS One Zone-IA)