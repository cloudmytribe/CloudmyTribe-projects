# Your Cloud Resume: Host Your Static Website on AWS

## MILESTONE 1 -> Deploying with the AWS Console 🚀

### Step-by-Step Guide 

#### 1. Review the Challenge Requirements
- **Action**: Thoroughly read through the requirements of the challenge to understand the expectations and goals.
- **Outcome**: A clear understanding of the objectives and deliverables.

#### 2. Explore AWS Documentation
- **Action**: Dive into AWS documentation to familiarize yourself with the services needed for this challenge. Focus on:
  - Amazon S3 (for static website hosting)
  - AWS CloudFront (for CDN)
  - Route 53 (for DNS management)
  - IAM (for access management)
- **Outcome**: Knowledge of the services you'll be using, including best practices and configurations.

#### 3. Build Your Architecture Diagram
- **Action**: Design an architecture diagram that outlines the structure of your static website hosting solution. Use tools like draw.io, Lucidchart, or any diagramming tool you're comfortable with.
  - Include components like S3 bucket, CloudFront distribution, Route 53, and IAM roles/policies.
- **Outcome**: A comprehensive architecture diagram that visually represents the infrastructure.

#### 4. HTML

 Your resume needs to be written in [HTML](https://developer.mozilla.org/en-US/docs/Web/HTML). Not a Word doc, not a PDF. [Example](https://codepen.io/emzarts/pen/OXzmym).

#### 5. CSS (style.css)
Your resume needs to be styled with [CSS](https://www.w3schools.com/css/). It doesn't have to be fancy. But we need to see something other than raw HTML when we open the webpage. Feel free to get creative.

#### 6. Static Website (index.html)
Your HTML resume should be deployed online as an [Amazon S3 static website](https://docs.aws.amazon.com/AmazonS3/latest/dev/WebsiteHosting.html). Explicitly Use S3. 

#### 7. HTTPS
The S3 website URL should use [HTTPS](https://www.cloudflare.com/learning/ssl/what-is-https/) for security. You will need to use [Amazon CloudFront](https://aws.amazon.com/blogs/networking-and-content-delivery/amazon-s3-amazon-cloudfront-a-match-made-in-the-cloud/) to help with this.

#### 8. DNS
Point a custom DNS domain name to the CloudFront distribution, so your resume can be accessed at something like `abel-morara.com`. You can use [Amazon Route 53](https://aws.amazon.com/route53/) or any other DNS provider for this.

- 
#### 9. Document Your Progress
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

#### 10. Create a Screen Recording or Deploy a Live Website (Optional)
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

## 👀 Sneak Peak to Milestone 2: Provisioning your Infrastructure as code 👁️👁️
