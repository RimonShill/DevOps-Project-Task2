
<!-- ABOUT THE PROJECT -->
## About The Project

E-commerce website on cloud

Network, Application Diagram and Architecture to host and monitor a e-commerce website on AWS cloud in efficient manner.
Services used are chosen in such a way that they will provide maximum throughput along with cost saving.
![Network Diagram](images/Network.png?raw=true "Network Diagram")





<!-- GETTING STARTED -->
## Getting Started

To get a local copy up and running follow these simple steps.

### Prerequisites

All you need is a AWS account.Building these services and deploying is relatively easy.Ping me if you need help.
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


<!-- USAGE EXAMPLES -->
## Usage

Use this architecture to host and monitor a e-commerce website on AWS cloud in efficient manner.


<!-- ROADMAP -->
## Roadmap

See the [open issues](https://github.com/Rekid46/AWS-architecture-for-ecommerce-website/issues) for a list of proposed features (and known issues).



<!-- CONTRIBUTING -->
## Contributing

Contributions are what make the open source community such an amazing place to be learn, inspire, and create. Any contributions you make are **greatly appreciated**.

1. Fork the Project
2. Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3. Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the Branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request



<!-- LICENSE -->
## License

Distributed under the Apache License. See `LICENSE` for more information.



<!-- CONTACT -->
## Contact

Ranjan Singh : [@twitter_handle](https://twitter.com/lifeofranjan) 

Email : Singhranjan9024@gmail.com

Project Link: [https://rekid46.github.io/AWS-architecture-for-ecommerce-website/](https://rekid46.github.io/AWS-architecture-for-ecommerce-website/)






<!-- MARKDOWN LINKS & IMAGES -->
<!-- https://www.markdownguide.org/basic-syntax/#reference-style-links -->
[contributors-shield]: https://img.shields.io/github/contributors/Rekid46/AWS-architecture-for-ecommerce-website.svg?style=for-the-badge
[contributors-url]: https://github.com/Rekid46/AWS-architecture-for-ecommerce-website/graphs/contributors
[forks-shield]: https://img.shields.io/github/forks/Rekid46/AWS-architecture-for-ecommerce-website.svg?style=for-the-badge
[forks-url]: https://github.com/Rekid46/AWS-architecture-for-ecommerce-website/network/members
[stars-shield]: https://img.shields.io/github/stars/Rekid46/AWS-architecture-for-ecommerce-website.svg?style=for-the-badge
[stars-url]: https://github.com/Rekid46/AWS-architecture-for-ecommerce-website/stargazers
[issues-shield]: https://img.shields.io/github/issues/Rekid46/AWS-architecture-for-ecommerce-website.svg?style=for-the-badge
[issues-url]: https://github.com/Rekid46/AWS-architecture-for-ecommerce-website/issues
[license-shield]: https://img.shields.io/github/license/Rekid46/AWS-architecture-for-ecommerce-website.svg?style=for-the-badge
[license-url]: https://github.com/Rekid46/AWS-architecture-for-ecommerce-website/blob/master/LICENSE.txt
[linkedin-shield]: https://img.shields.io/badge/-LinkedIn-black.svg?style=for-the-badge&logo=linkedin&colorB=555
[linkedin-url]: https://www.linkedin.com/in/ranjan-singh-335845206/
