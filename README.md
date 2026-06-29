# AWS-Resume-Website-Deployment-Using-EC2-Nginx-Cloudfront

## Project Overview
This project demonstrates hosting a personal resume website using AWS EC2 with Nginx as a web server and CloudFront for secure global content delivery (HTTPS + CDN optimization).

## Tech Stack
- AWS EC2 (Amazon Linux)
- Nginx Web Server
- AWS CloudFront (CDN)
- HTML, CSS (Static Resume Website)

## Architecture
```mermaid
flowchart TD
    U[User Browser]

    CF[CloudFront Distribution<br/>HTTPS + Caching]

    EC2[EC2 Instance]

    N[Nginx Web Server]

    DIR[/usr/share/nginx/html/]

    HTML[index.html]


    U --> CF
    CF --> EC2
    EC2 --> N
    N --> DIR

    DIR --> HTML

    CF -. Origin Request .-> EC2
```



## Features
- Deployed static resume website on EC2
- Configured Nginx for serving static files
- Enabled HTTPS access via CloudFront
- Secure and scalable hosting setup

## Deployment Steps
**Step 1:** Launch EC2 instance. 
Create instance (Amazon Linux 2/2023)  
Allow HTTP (80) and SSH (22) in Security Group  
**Step 2:** Install & Start Nginx
Installed Nginx on Amazon Linux using yum.
Started and enabled Nginx service.  
**Step 3:** Deploy Website Files
Navigated to /usr/share/nginx/html/ directory.
Uploaded index.html, CSS, JS, and assets.
Restarted Nginx service.  
**Step 4:** Test EC2 Deployment
Accessed website using EC2 Public IP.
Verified Nginx default server was serving custom site.
**Step 5:** Configure CloudFront
Created CloudFront distribution.
Selected EC2 Public IP as custom origin.
Enabled HTTPS redirect and caching.
**Step 6:** Deploy & Access Website
Waited for CloudFront deployment to complete.
Accessed website using CloudFront domain URL.
