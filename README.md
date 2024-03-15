
<!-- ABOUT THE PROJECT -->
## About The Project

E-commerce website on cloud

Network, Application Diagram and Architecture to host and monitor a e-commerce website on AWS cloud in efficient manner.
Services used are chosen in such a way that they will provide maximum throughput along with cost saving.
![Network Diagram](Network.png?raw=true "Network Diagram")





<!-- GETTING STARTED -->
## Getting Started

To get a local copy up and running follow these simple steps.

### Prerequisites

* AWS account 


### Installation

Description:
1. We will use M4 type EC2 instance to bear high computation and storage.
2. Create a AMI with the instance and assign a Auto Scaling group.
3. A Elastic Load Balancer with stickiness enabled to balance the network traffic efficiently.
4. For backend database we will use RDS with multiple read replicas to store user data.
5. AWS ElastiCache for fast performance and less reads from database using cache.
6. We will use aws sns for email,text and other notifications.
7. Amazon Cloudwatch for continuous health check and monitoring.
8. Aws S3 for Static content and images and thumbnails.
9. AWS Route53 for DNS and routing.
10. AWS Cloudfront for for fast access to website through edge locations or delivering application.
11. Aws cognito for identity check/credential check.
12. Moreover we will use web clients for storing cookies and making website stateless.


Step-wise description:
1. User will access website and will be directed to route 53.
2. Route 53 will direct the traffic towards Cloudfront which serves data or point towards ELB depending upon scenario along with cognito checking identity.
3. ELB will direct traffic to EC2 ASG instances.
4. Static website data like product images and thumbnails will be served through aws s3.
5. ELB sticky session will make sure that user is connected to same instance.
6. For database EC2 instance will check Elasticache if it is a cache-hit it will server data or it will look into RDS and cache data.
7. Finally the data is served back to customer.
8. SNS will help in notification services like order confirmation calls or other notifications (Using lambda function or APIs)
9. CloudWatch will help to Monitor.

Security Perspective:
- Tight Security with security groups referencing each other. No instance or Database will be publicly accessible.
