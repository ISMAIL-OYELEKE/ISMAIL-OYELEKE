<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:0d1117,55:0e7490,100:22d3ee&height=140&section=header" width="100%" alt="Header" />

<h1>Ismail Oyeleke</h1>

<p><b>Cloud Engineer | AWS Infrastructure, Terraform and CI/CD</b></p>

<a href="https://github.com/ISMAIL-OYELEKE">
  <img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=600&size=22&duration=3200&pause=1000&color=22d3ee&center=true&vCenter=true&width=760&lines=AWS+Infrastructure+and+Serverless+Applications;Terraform%2C+CI%2FCD+and+Containers;Production+Web+Apps+for+Real+Businesses;Open+to+Cloud+and+DevOps+Roles" alt="Typing animation" />
</a>

<br/><br/>

![BSc](https://img.shields.io/badge/BSc_Computer_Science-Kwara_State_University-164e63?style=for-the-badge&logo=googlescholar&logoColor=white)
![Honors](https://img.shields.io/badge/First_Class_Honors-CGPA_3.85%2F4.00-155e75?style=for-the-badge)
![Location](https://img.shields.io/badge/Location-Lagos%2C_Nigeria-0e7490?style=for-the-badge&logo=googlemaps&logoColor=white)

<a href="https://ismailoyeleke.com/"><img src="https://img.shields.io/badge/Portfolio-ismailoyeleke.com-0891b2?style=for-the-badge&logo=googlechrome&logoColor=white" alt="Portfolio" /></a>
<a href="https://www.linkedin.com/in/ismail-oyeleke-6930b6317/"><img src="https://img.shields.io/badge/LinkedIn-Connect-0891b2?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn" /></a>
<a href="mailto:ismailoyeleke2003@gmail.com"><img src="https://img.shields.io/badge/Gmail-Email_Me-0e7490?style=for-the-badge&logo=gmail&logoColor=white" alt="Email" /></a>
<a href="https://github.com/ISMAIL-OYELEKE"><img src="https://img.shields.io/badge/GitHub-ISMAIL--OYELEKE-164e63?style=for-the-badge&logo=github&logoColor=white" alt="GitHub" /></a>

<br/>

![Followers](https://img.shields.io/github/followers/ISMAIL-OYELEKE?style=flat-square&color=0e7490&label=Followers&logo=github)

</div>

---

## About

I'm a Cloud Engineer based in Lagos, Nigeria, focused on AWS infrastructure, serverless applications and deployment automation. I design systems around reliability and access control first, then automate how they ship.

My cloud work covers CI/CD pipelines, infrastructure as code with Terraform and CloudFormation, containerised workloads on ECS, EKS and Fargate, and CloudWatch monitoring. My backend foundation is ASP.NET Core, REST APIs, JWT authentication and relational databases.

I also build and maintain production web apps for small businesses. That includes a point-of-sale and inventory system a retail shop uses daily, where stock, payments and audit logs are updated together inside Postgres functions, so the books never drift out of sync.

**Product mindset:** I care about what happens after deployment, including who can access what, how failures are recovered and how the next developer picks the system up.

**Open to**

- Cloud, DevOps, Platform and Cloud Support roles
- Relocation with employer sponsorship
- Remote roles that can hire from Nigeria

---

## Tech Stack

<div align="center">

**Languages**

<img src="https://skillicons.dev/icons?i=python,cs,js,ts,bash&theme=dark" alt="Languages" />

**Frontend**

<img src="https://skillicons.dev/icons?i=html,react,nextjs,tailwind&theme=dark" alt="Frontend" />

**Backend and Databases**

<img src="https://skillicons.dev/icons?i=dotnet,nodejs,nestjs,postgres,supabase&theme=dark" alt="Backend and databases" />

Also: ASP.NET Core, Entity Framework Core, SQL Server, REST APIs, JWT

**Cloud, DevOps and Tooling**

<img src="https://skillicons.dev/icons?i=aws,terraform,docker,kubernetes,jenkins,githubactions,gitlab,linux,git,vercel,cloudflare&theme=dark" alt="Cloud and DevOps" />

AWS services: Lambda, API Gateway, DynamoDB, EventBridge, SES, S3, CloudFront, Route 53, VPC, EC2, RDS, IAM, CloudWatch, ECS, EKS, Fargate, Secrets Manager, Lex, Connect, Polly

</div>

---

## Applied AI on AWS

| Domain | Level | Details |
|:--|:--|:--|
| Conversational AI and NLU | Applied, project work | Amazon Lex intents with a 0.70 confidence threshold, fallback handling and Python Lambda fulfilment for a recruiter-facing assistant |
| Speech services | Applied, client work | Amazon Polly text-to-speech greetings inside an Amazon Connect contact centre |

---

## Featured Projects

<details>
<summary><b>Kestrel Loan Platform</b> | payday-proof microfinance loan platform on AWS</summary>

<br/>

A loan platform for a microfinance bank, built on AWS in five days from a brief, tested at 25 times normal payday traffic, then torn down for about USD 9.20. It replaces a single server that went down almost every month when salaries landed and scored loans overnight.

| | |
|:--|:--|
| **Stack** | Terraform, ECS Fargate, Application Load Balancer, WAF, RDS PostgreSQL (Multi-AZ), SQS, Lambda, KMS, CloudWatch, GitHub Actions, Python, Docker |
| **Architecture** | API on Fargate across two Availability Zones with auto scaling and a higher minimum on payday, loans scored seconds after arrival by a Lambda behind an SQS queue with a dead-letter queue, and a database lock so a repeated message never produces two decisions |
| **Security** | BVN encrypted with KMS plus an HMAC lookup hash, so it never appears in the database, logs or API responses. No internet route for servers or database (VPC endpoints only), CloudTrail audit log, GuardDuty, Security Hub and AWS Config |
| **Delivery** | Lint, tests, Checkov and a Terraform plan on every pull request, GitHub Actions signing in to AWS with OIDC instead of access keys, and a human approval before prod |
| **Results** | Load test: 19,602 requests, 0 failed, p95 of 58 ms against a 1 second target. Restore drill: newest restore point 4 min 44 s old, service stable 21 minutes after the restore started. Deliberately broken deployment rolled back by itself |
| **Repository** | [View on GitHub](https://github.com/ISMAIL-OYELEKE/kestrel-platform) |

Includes ten architecture decision records, a runbook, a design document and screenshot evidence for each requirement. Write-ups: [case study](https://ismailoyeleke.com/projects/kestrel-loan-platform), [video walkthrough](https://youtu.be/dCuNLgKuf78) and [Medium article](https://medium.com/@ismailoyeleke2003/i-built-a-loan-platform-on-aws-broke-it-on-purpose-and-tore-it-down-for-usd-9-20-e758f948ecd4).

</details>

<details>
<summary><b>Serverless Staff Portal</b> | leave and payroll-advance workflows on AWS</summary>

<br/>

A decoupled serverless application that moves staff leave and payroll-advance requests through approval stages, with automated notifications at each step. Built during my time at Cloud Chariots.

| | |
|:--|:--|
| **Stack** | AWS Lambda, API Gateway, DynamoDB, Amazon SES, EventBridge |
| **Architecture** | Pay-per-use serverless backend, DynamoDB for application data and session storage, scheduled workflow notifications through EventBridge |
| **Security** | Role-based access control and input validation across staff and admin workflows |
| **Status** | Delivered for an employer |
| **Repository** | Private (employer work) |

Event-driven design: a request triggers the next approval stage and the right email, and the whole system scales to zero when nobody is using it.

</details>

<details>
<summary><b>Multi-Tier AWS Web Application</b> | highly available three-tier deployment</summary>

<br/>

A WordPress-style web application deployed across multiple Availability Zones, with the database and app tiers kept off the public internet.

| | |
|:--|:--|
| **Stack** | VPC, EC2, RDS, Application Load Balancer, Auto Scaling, Secrets Manager |
| **Architecture** | Custom VPC, public and private subnets, load-balanced web tier, managed database tier |
| **Security** | Private subnets for backend tiers, database credentials held in Secrets Manager |
| **Automation** | LAMP stack installed through an EC2 user-data bootstrap script |
| **Repository** | [View on GitHub](https://github.com/ISMAIL-OYELEKE/Project-3-Enterprise-Multi-Tier-Web-App-Deployment) |

Includes the architecture write-up, deployment guide and the bootstrap script.

</details>

<details>
<summary><b>Serverless Recruiter Chatbot</b> | Amazon Lex and Lambda assistant</summary>

<br/>

An intent-based assistant on my portfolio site that answers recruiter questions about my skills, projects, certifications and contact details.

| | |
|:--|:--|
| **Stack** | Amazon Lex, AWS Lambda, Python, IAM, CloudWatch |
| **Architecture** | Lex handles intent recognition, a Python Lambda handler returns predefined responses per intent |
| **NLU tuning** | Confidence threshold set to 0.70 with fallback responses for unsupported questions |
| **Security** | Least-privilege IAM permissions, CloudWatch logs for debugging |
| **Repository** | [View on GitHub](https://github.com/ISMAIL-OYELEKE/Project-4-Serverless-Chatbot-Build-an-AI-powered-chatbot-with-AWS-Lex-Lambda) |

</details>

<details>
<summary><b>Cloud Contact Centre</b> | Amazon Connect for a microfinance client</summary>

<br/>

An omnichannel contact centre with voice and web chat, built for a microfinance client.

| | |
|:--|:--|
| **Stack** | Amazon Connect, Amazon Polly, Web Chat, JavaScript |
| **Architecture** | Inbound routing flows with Africa/Lagos business-hours logic, agent queues and routing profiles |
| **Security** | Chat widget restricted to allowed domains |
| **Status** | Delivered for a client |
| **Repository** | Private (client work), with a [public test portal](https://github.com/ISMAIL-OYELEKE/cloud-chariots-amazon-connect-test-portal) for trying the chat flow |

</details>

<details>
<summary><b>Retail POS and Inventory System</b> | live in production</summary>

<br/>

A point-of-sale and inventory system used daily by a phone and gadget retail shop in Nigeria. It records sales, prints invoices, tracks stock by IMEI or serial number and follows up on part-paid debts.

| | |
|:--|:--|
| **Stack** | Next.js, React, TypeScript, Supabase (Postgres, auth, row-level security), Tailwind CSS, shadcn/ui, Vercel |
| **Architecture** | Sales and payments run only through two Postgres functions, so stock, totals, payments and the audit log change in a single transaction |
| **Security** | Admin and staff roles, row-level security, security-definer functions that enforce their own checks, forced password change on first login, account deactivation, admin audit logs |
| **Delivery** | Pull-request workflow, Vercel preview deployments, dated SQL migrations with rollback copies kept in the repository |
| **Repository** | Private (client work) |

</details>

<details>
<summary><b>Company Website</b> | hardened static site for an AWS consultancy</summary>

<br/>

A marketing website for an AWS cloud consulting company in Lagos, live at [clouddimex.com](https://clouddimex.com).

| | |
|:--|:--|
| **Stack** | Next.js (App Router, static export), Tailwind CSS, Three.js hero, Vercel |
| **Security** | Content Security Policy with per-script SHA-256 hashes, HSTS with preload, frame protection, consent-gated analytics, hCaptcha on the contact form |
| **Quality** | Automated scripts for WCAG AA contrast, broken links, security headers, CSP violations, layout overflow and form behaviour |
| **Repository** | Private (client work) |

</details>

---

## Experience

### Cloud/DevOps Engineer | Cloud Chariots
`May 2026 to Aug 2026` | Hybrid, Lagos, Nigeria

Built and operated the delivery and infrastructure layer for internal applications on AWS.

- Built and maintained CI/CD pipelines using Jenkins, GitHub Actions and GitLab CI to automate build, test and deployment workflows
- Provisioned AWS infrastructure with Terraform and CloudFormation so environments are repeatable and version-controlled
- Containerised workloads and deployed them on Amazon ECS, EKS and Fargate with a high-availability design for internal users
- Implemented CloudWatch monitoring to support incident detection and troubleshooting
- Delivered the serverless staff portal and a contact centre for a microfinance client

![AWS](https://img.shields.io/badge/AWS-164e63?style=flat-square) ![Terraform](https://img.shields.io/badge/Terraform-155e75?style=flat-square) ![CloudFormation](https://img.shields.io/badge/CloudFormation-0e7490?style=flat-square) ![Jenkins](https://img.shields.io/badge/Jenkins-0891b2?style=flat-square) ![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-155e75?style=flat-square) ![ECS](https://img.shields.io/badge/ECS_EKS_Fargate-06b6d4?style=flat-square) ![CloudWatch](https://img.shields.io/badge/CloudWatch-0891b2?style=flat-square)

### Freelance Full-Stack Developer | Independent
`Freelance` | Nigeria

Built and maintain web applications for small business clients, from requirements through deployment.

- Built a production point-of-sale and inventory system with transactional money handling, role-based access and audit logging
- Built a hardened marketing website with strict security headers and an automated QA suite
- Work through pull requests with preview deployments, and ship database changes as reviewed, reversible migrations

![Next.js](https://img.shields.io/badge/Next.js-164e63?style=flat-square) ![TypeScript](https://img.shields.io/badge/TypeScript-155e75?style=flat-square) ![Supabase](https://img.shields.io/badge/Supabase-0e7490?style=flat-square) ![PostgreSQL](https://img.shields.io/badge/PostgreSQL-0891b2?style=flat-square) ![Vercel](https://img.shields.io/badge/Vercel-155e75?style=flat-square)

### C# .NET Developer, Intern | KGE Technologies
`Jul 2025 to Dec 2025` | Remote, Chennai, India

- Built and maintained REST APIs with ASP.NET Core
- Implemented JWT-based authentication and access control for backend services
- Worked with Entity Framework Core on database operations and query optimisation
- Delivered changes with Git and Agile workflows

![ASP.NET Core](https://img.shields.io/badge/ASP.NET_Core-164e63?style=flat-square) ![C#](https://img.shields.io/badge/C%23-155e75?style=flat-square) ![EF Core](https://img.shields.io/badge/Entity_Framework_Core-0e7490?style=flat-square) ![JWT](https://img.shields.io/badge/JWT-0891b2?style=flat-square)

### IT Support Specialist, Intern | Federal Airports Authority of Nigeria (FAAN)
`Sep 2023 to Feb 2024` | On-site, Lagos, Nigeria

- Provided support for computer hardware, network connectivity and IT configuration issues
- Diagnosed and resolved user incidents and carried out routine system maintenance

![Networking](https://img.shields.io/badge/Networking-164e63?style=flat-square) ![Troubleshooting](https://img.shields.io/badge/Incident_Resolution-155e75?style=flat-square) ![Hardware](https://img.shields.io/badge/IT_Support-0e7490?style=flat-square)

---

## Achievements

<div align="center">

| Recognition | Details |
|:--|:--|
| First Class (Honors), BSc Computer Science | Kwara State University, CGPA 3.85/4.00, September 2024 |
| AWS Certified Solutions Architect Associate | Validated design of secure, resilient and cost-aware AWS architectures |
| KCNA: Kubernetes and Cloud Native Associate | Foundational Kubernetes and cloud native certification |
| Production system in daily use | Built and maintain a point-of-sale system that a retail shop in Nigeria runs its sales on |

</div>

---

## Certifications

<div align="center">

**AWS**

![SAA](https://img.shields.io/badge/Solutions_Architect-Associate-164e63?style=for-the-badge&logo=amazonaws&logoColor=white)
![CCP](https://img.shields.io/badge/Cloud_Practitioner-Foundational-155e75?style=for-the-badge&logo=amazonaws&logoColor=white)
![Partner](https://img.shields.io/badge/AWS_Partner-Technical_Accredited-0e7490?style=for-the-badge&logo=amazonaws&logoColor=white)

**Cloud Native**

![KCNA](https://img.shields.io/badge/KCNA-Kubernetes_and_Cloud_Native_Associate-0e7490?style=for-the-badge&logo=kubernetes&logoColor=white)

**Multi-Cloud and Training**

![Aviatrix](https://img.shields.io/badge/Aviatrix-Multi--Cloud_Associate-0891b2?style=for-the-badge)
![ALX](https://img.shields.io/badge/ALX-Cloud_Practitioner-155e75?style=for-the-badge)

</div>

---

## Writing and Community

<div align="center">

<a href="https://medium.com/@ismailoyeleke2003"><img src="https://img.shields.io/badge/Medium-Technical_Blog-164e63?style=for-the-badge&logo=medium&logoColor=white" alt="Medium" /></a>
<a href="https://www.youtube.com/@learn_with_ismail_oyeleke"><img src="https://img.shields.io/badge/YouTube-Learn_With_Ismail-155e75?style=for-the-badge&logo=youtube&logoColor=white" alt="YouTube" /></a>
<a href="https://x.com/ismail_oyeleke_"><img src="https://img.shields.io/badge/X-Follow-0e7490?style=for-the-badge&logo=x&logoColor=white" alt="X" /></a>

</div>

---

## GitHub Analytics

<div align="center">

<img src="https://github-readme-stats.vercel.app/api?username=ISMAIL-OYELEKE&show_icons=true&hide_border=true&bg_color=0d1117&title_color=22d3ee&text_color=c9d1d9&icon_color=67e8f9" height="170" alt="GitHub stats" />
<img src="https://github-readme-stats.vercel.app/api/top-langs/?username=ISMAIL-OYELEKE&layout=compact&hide_border=true&bg_color=0d1117&title_color=22d3ee&text_color=c9d1d9" height="170" alt="Top languages" />

<br/>

<img src="https://streak-stats.demolab.com?user=ISMAIL-OYELEKE&theme=dark&hide_border=true&background=0D1117&ring=22d3ee&fire=67e8f9&currStreakNum=a5f3fc&sideNums=c9d1d9&currStreakLabel=22d3ee&sideLabels=67e8f9&dates=8b949e" alt="Streak stats" />

</div>

---

## Contribution Snake

<div align="center">

<img src="https://raw.githubusercontent.com/ISMAIL-OYELEKE/ISMAIL-OYELEKE/output/github-snake-dark.svg?v=cyan" width="100%" alt="Contribution snake" />

</div>

---

## Current Focus

```yaml
learning:
  - Terraform module design
  - Kubernetes
  - Serverless architecture patterns
building:
  - Production web apps for small business clients
  - AWS projects that show infrastructure done properly
exploring:
  - AI-integrated applications on AWS
open_to:
  - Cloud, DevOps and Platform roles
  - Relocation with sponsorship or remote work from Nigeria
```

---

## Connect

<div align="center">

<a href="mailto:ismailoyeleke2003@gmail.com"><img src="https://img.shields.io/badge/Gmail-ismailoyeleke2003-0e7490?style=for-the-badge&logo=gmail&logoColor=white" alt="Gmail" /></a>
<a href="https://www.linkedin.com/in/ismail-oyeleke-6930b6317/"><img src="https://img.shields.io/badge/LinkedIn-Ismail_Oyeleke-0891b2?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn" /></a>
<a href="https://github.com/ISMAIL-OYELEKE"><img src="https://img.shields.io/badge/GitHub-ISMAIL--OYELEKE-164e63?style=for-the-badge&logo=github&logoColor=white" alt="GitHub" /></a>
<a href="https://ismailoyeleke.com/"><img src="https://img.shields.io/badge/Portfolio-ismailoyeleke.com-0891b2?style=for-the-badge&logo=googlechrome&logoColor=white" alt="Portfolio" /></a>

</div>

---

<div align="center">

<i>Build it so it runs without you, then document it so anyone can take over.</i>

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:0d1117,55:0e7490,100:22d3ee&height=120&section=footer" width="100%" alt="Footer" />

</div>
