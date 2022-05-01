# aws-s3-bucket-as-maven-repository
An AWS S3 Bucket can be used as an inexpensive option to store Maven build artifacts or other binary artifacts. 

It’s an alternative to feature-rich Maven repository managers like Nexus and Artifactory when you don’t have the resources to install and maintain a server with the required software or the budget to subscribe to a hosted plan.

This solution would be valid for a solo developer or a small team. 
Although a better choice than checking in the resulting build artifacts into the SCM, it has some limitations: 
    - You won’t be able to Search for an artifact, which is convenient when you need to find out the artifactId, groupId and version of a           dependency. 
    - You will also need to maintain the repository by manually removing older versions of artifacts as the snapshot folder grows overtime.

A solution to these problems could be automated when using a feature-rich Maven repository manager like Nexus or Artifactory but this will more expensive than using an s3 bucket.

This mini project covers setting up an AWS S3 bucket and configuring Maven to store its build artifacts in the s3 bucket. 

Steps:
======
1. Define / configure s3 bucket in a bucket.tf, terraform configuration file.
2. Provision the bucket using terraform
3. Configure maven build server to use the s3 bucket as its maven repository.

