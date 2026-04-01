# AWS Cloud Resume

A static resume/portfolio website deployed on AWS cloud infrastructure using S3, CloudFront, and IAM.

**Live site:** [d1yqvb88zdhsd6.cloudfront.net](https://d1yqvb88zdhsd6.cloudfront.net)

## Architecture

```
User visits URL
      |
      v
[CloudFront CDN] -- serves cached content from edge locations worldwide
      |                (HTTPS encrypted automatically)
      v
[S3 Bucket] -- stores the website files (index.html)
      |          (private - no public access)
      v
[IAM / OAC] -- Origin Access Control ensures only CloudFront
               can read from the S3 bucket
```

## AWS Services Used

- **Amazon S3** - Static website file storage. Bucket is configured with Block Public Access enabled, so files are not directly accessible from the internet.
- **Amazon CloudFront** - Content Delivery Network (CDN) that distributes the website globally from edge locations. Provides HTTPS encryption and caching for fast load times.
- **IAM / Origin Access Control (OAC)** - Restricts S3 bucket access so that only the CloudFront distribution can retrieve files. Follows the principle of least privilege.

## Security

- S3 bucket has Block Public Access enabled
- CloudFront is the only access point to the content (via OAC)
- HTTPS is enforced through CloudFront
- No WAF needed for a static site with no user input or backend

## Tech Stack

- HTML5 / CSS3
- Google Fonts (DM Sans, DM Mono)
- AWS Free Tier

## Author

**Artem Kozlov** - U.S. Army Veteran | Cloud Engineering Student
- [LinkedIn](https://linkedin.com/in/artem-kozlov-v)
- [GitHub](https://github.com/artemkoz99)
