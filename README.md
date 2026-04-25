# World Map Tracker

**[Live Demo](https://d3rfup3qdmix7x.cloudfront.net)**

A high-performance, interactive mapping application designed for global data visualization. Built with vanilla JavaScript and Leaflet.js, this project delivers a rich spatial experience prioritizing speed and dependency minimization.

## Cloud Infrastructure & Scalability

The application is deployed on AWS using a robust, repeatable Infrastructure-as-Code (IaC) pipeline. 

* **Provisioning:** Fully automated via **Terraform** to ensure deterministic deployments and eliminate configuration drift.
* **Serverless Hosting:** Served securely via **Amazon CloudFront (CDN)**, which edge-caches the static assets hosted in a fully private **AWS S3 Bucket**.
* **Auto-Scaling & CDN:** Inherently scales to handle sudden traffic spikes and delivers low-latency content globally without requiring load balancers.
* **Security:** Enforces strict HTTPS and uses Origin Access Control (OAC) to ensure the underlying S3 bucket is completely isolated from direct public access.

## Engineering Decisions & The "Why"

* **Infrastructure-as-Code (IaC):** Adopted Terraform over manual AWS console configuration to guarantee consistent, version-controlled environments and rapid disaster recovery.
* **Zero-Maintenance Architecture:** Utilizing a serverless CloudFront + S3 architecture to drastically reduce operational costs, enforce HTTPS, and improve global scalability over traditional EC2 hosting.
* **Zero-Dependency Core Logic:** Chosen vanilla JavaScript over heavy frontend frameworks to maximize render performance for dynamic map objects and reduce time-to-interactive.
* **Open-Source Mapping:** Leveraged Leaflet.js with OpenStreetMap tile layers to bypass vendor lock-in and avoid the restrictive rate limits and high costs associated with proprietary mapping APIs.

## Repository Structure

```text
.
├── map-infra/                 # Infrastructure as Code
│   ├── main.tf                # Terraform configuration (S3 Bucket, IAM Policies)
│   └── .terraform.lock.hcl    # Terraform dependency lockfile
├── index.html                 # Main application entry point & UI
└── README.md                  # Project documentation
```

## Tech Stack
* **Frontend:** Vanilla JavaScript, HTML5, CSS3, Leaflet.js
* **Mapping:** OpenStreetMap
* **Infrastructure:** AWS (CloudFront, S3), Terraform