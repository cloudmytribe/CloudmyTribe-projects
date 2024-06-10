# Welcome to CloudmyTribe Community Project Challenges! 🤝

## Table of Contents
1. [Introduction](#introduction-)
2. [How to Get Started](#how-to-get-started)
3. [Your Cloud Resume Challenge: Host Your Static Website on AWS](#your-cloud-resume-challenge-host-your-static-website-on-aws)
   - [Milestone 1: Deploying with the AWS Console](#milestone-1--deploying-with-the-aws-console-)
     - [Step-by-Step Guide](#step-by-step-guide)
       - [Review the Challenge Requirements](#review-the-challenge-requirements)
       - [Explore AWS Documentation](#explore-aws-documentation)
       - [Build Your Architecture Diagram](#build-your-architecture-diagram)
       - [Create Your HTML Resume](#create-your-html-resume)
       - [Style Your Resume with CSS](#style-your-resume-with-css)
       - [Deploy Your Resume as a Static Website on S3](#deploy-your-resume-as-a-static-website-on-s3)
       - [Enable HTTPS with CloudFront](#enable-https-with-cloudfront)
       - [Set Up Custom DNS with Route 53](#set-up-custom-dns-with-route-53)
       - [Configure IAM for Access Management](#configure-iam-for-access-management)
       - [Document Your Progress](#document-your-progress)
       - [Create a Screen Recording or Deploy a Live Website (Optional)](#create-a-screen-recording-or-deploy-a-live-website-optional)
     - [Deliverables](#deliverables-)
   - [Sneak Peak to Milestone 2](#sneak-peak-to-milestone-2-provisioning-your-infrastructure-as-code-)

## Introduction 👋

Welcome to the CloudmyTribe Cloud Challenge projects! This initiative is designed to help you build cloud-based products using AWS services. Whether you're just getting started with cloud technologies or looking to sharpen your skills, these projects offer a comprehensive, hands-on experience.
 
---


# Your Cloud Resume Challenge: Host Your Static Website on AWS

## MILESTONE 1 -> Deploying with the AWS Console 🚀

### Step-by-Step Guide

### How to Get Started
1. **Prepare Your Tools**
   - Ensure you have the necessary tools and accounts set up, including an **AWS account**, **GitHub account**, and a **gitpod** as your recommended CDE all connected to offer a seamless coding space.
   - If you have a problem setting up the environments please refer to the live session recording or ask for assitance on the slack channel and google classrooms.

#### 2. Explore AWS Documentation
- **Action**: Dive into AWS documentation to familiarize yourself with the services needed for this challenge. Focus on:
  - [Amazon S3 (for static website hosting)](https://docs.aws.amazon.com/AmazonS3/latest/dev/WebsiteHosting.html)
  - [AWS CloudFront (for CDN)](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/Introduction.html)
  - [Route 53 (for DNS management)](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/Welcome.html)
  - [IAM (for access management)](https://docs.aws.amazon.com/IAM/latest/UserGuide/introduction.html)
- **Outcome**: Knowledge of the services you'll be using, including best practices and configurations.

#### 3. Build Your Architecture Diagram
- **Action**: Design an architecture diagram that outlines the structure of your static website hosting solution. Use tools like [draw.io](https://www.diagrams.net/), [Lucidchart](https://www.lucidchart.com/), or any diagramming tool you're comfortable with.
  - Include components like S3 bucket, CloudFront distribution, Route 53, and IAM roles/policies.
- **Outcome**: A comprehensive architecture diagram that visually represents the infrastructure.

#### 4. Create Your HTML Resume
- **Action**: Write your resume in [HTML](https://developer.mozilla.org/en-US/docs/Web/HTML). Not a Word doc, not a PDF. [Example](https://codepen.io/emzarts/pen/OXzmym).
- **Outcome**: A basic HTML file containing your resume.

#### 5. Style Your Resume with CSS
- **Action**: Apply styling to your resume using [CSS](https://www.w3schools.com/css/). It doesn't have to be fancy, but it should be more than just raw HTML. Feel free to get creative.
- **Outcome**: A styled HTML resume file.

#### 6. Deploy Your Resume as a Static Website on S3
- **Action**: Follow the steps below to deploy your HTML resume as a static website on S3.
  - **Create an S3 Bucket**:
    - Open the [Amazon S3 console](https://s3.console.aws.amazon.com/s3/home).
    - Click on "Create bucket".
    - Enter a unique bucket name and select your region.
    - Uncheck "Block all public access" to make the bucket public.
    - Click "Create bucket".
  - **Upload Your Website Files**:
    - Open your bucket.
    - Click on "Upload" and add your HTML and CSS files.
    - Click "Upload".
  - **Configure the Bucket for Static Website Hosting**:
    - Open the "Properties" tab of your bucket.
    - Scroll down to "Static website hosting" and click "Edit".
    - Select "Enable" and specify your index document (e.g., index.html).
    - Click "Save changes".
  - **Set Permissions**:
    - Open the "Permissions" tab.
    - Click "Bucket Policy" and add a policy to make the bucket content publicly accessible. Use the policy generator to create a policy with the following template:
      ```json
      {
        "Version": "2012-10-17",
        "Statement": [
          {
            "Sid": "PublicReadGetObject",
            "Effect": "Allow",
            "Principal": "*",
            "Action": "s3:GetObject",
            "Resource": "arn:aws:s3:::your-bucket-name/*"
          }
        ]
      }
      ```
    - Replace `your-bucket-name` with the name of your S3 bucket.
    - Click "Save".

- **Outcome**: Your resume hosted on an S3 static website.

#### 7. Enable HTTPS with CloudFront
- **Action**: Use the following steps to enable HTTPS for your S3 website using CloudFront.
  - **Create a CloudFront Distribution**:
    - Open the [CloudFront console](https://console.aws.amazon.com/cloudfront/v2/home).
    - Click on "Create Distribution".
    - Choose "Web" and click "Get Started".
    - For "Origin Domain Name", select your S3 bucket from the list.
    - For "Viewer Protocol Policy", choose "Redirect HTTP to HTTPS".
    - Click "Create Distribution".
 

 - **Set Up SSL/TLS Certificate**:
    - Open the "Distributions" tab and select your distribution.
    - Click on the "Edit" button.
    - In the "SSL Certificate" section, choose "Default CloudFront Certificate" (for a domain like `*.cloudfront.net`) or use an ACM certificate for a custom domain.
    - Click "Save Changes".

- **Outcome**: Your resume accessible over HTTPS.

#### 8. Set Up Custom DNS with Route 53
- **Action**: Configure a custom domain to point to your CloudFront distribution using Route 53.
  - **Register a Domain**:
    - Open the [Route 53 console](https://console.aws.amazon.com/route53/home).
    - Click on "Domains" and then "Register Domain".
    - Follow the steps to register your domain.
  - **Create a Hosted Zone**:
    - In Route 53, click on "Hosted zones" and then "Create hosted zone".
    - Enter your domain name and click "Create hosted zone".
  - **Create an Alias Record**:
    - Open your hosted zone.
    - Click on "Create record".
    - Choose "Simple routing".
    - Enter your subdomain (e.g., www) and select "Alias to CloudFront distribution".
    - Select your CloudFront distribution from the list.
    - Click "Create records".

- **Outcome**: Your resume accessible at your custom domain.

#### 9. Configure IAM for Access Management
- **Action**: Set up IAM roles and policies to manage access to your AWS resources.
  - **Create an IAM Role**:
    - Open the [IAM console](https://console.aws.amazon.com/iam/home).
    - Click on "Roles" and then "Create role".
    - Choose "AWS service" and select "EC2".
    - Click "Next: Permissions" and attach the "AmazonS3FullAccess" policy.
    - Click "Next: Tags" and then "Next: Review".
    - Enter a role name and click "Create role".
  - **Create an IAM User**:
    - Open the IAM console.
    - Click on "Users" and then "Add user".
    - Enter a username and select "Programmatic access".
    - Click "Next: Permissions" and attach the "AmazonS3FullAccess" policy.
    - Click "Next: Tags" and then "Next: Review".
    - Click "Create user".

- **Outcome**: IAM roles and policies configured for access management.

#### 10. Document Your Progress
- **Action**: Start documenting your progress in a blog or GitHub README file. Structure it as follows:
  - **Introduction**:
    - Briefly introduce the challenge and its objectives.
    - Example: "This challenge aims to host a static website on AWS using services such as S3, CloudFront, and Route 53."
  - **Step-by-Step Guide**:
    - Detail each step you took to complete the tasks.
    - Include code snippets, configurations, and screenshots.
  - **Challenges Faced**:
    - Discuss any issues you encountered and how you resolved them.
  - **Key Takeaways**:
    - Summarize what you learned from the challenge.
  - **Resources**:
    - List any helpful resources or references.
    - Example: "AWS Documentation, CloudFormation templates, AWS tutorials."

- **Outcome**: A detailed and insightful blog post or README file documenting your journey.

#### 11. Create a Screen Recording or Deploy a Live Website (Optional)
- **Action**: 
  - **Screen Recording**: Record a video demonstrating the setup and functionality of your static website.
    - Use tools like OBS Studio or any screen recording software.
    - Include steps like accessing the S3 bucket, CloudFront configuration, and DNS setup in Route 53.
  - **Live Website**: Deploy your static website and make it accessible via a public URL.
    - Ensure the website is fully functional and accessible.
    - Share the URL in your documentation.

- **Outcome**: An interactive element showcasing your implementation, either through a video or a live website.

### Deliverables 📦

- **Architecture Diagram**: A visual representation of your cloud infrastructure.
- **Blog or GitHub README**: A comprehensive guide documenting your progress, challenges, and learnings.
- **Screen Recording or Live Website**: An optional, interactive showcase of your implementation.

___

## 👀 Sneak Peak to Milestone 2: Provisioning your Infrastructure as Code 👁️👁️
