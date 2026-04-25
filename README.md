# World Map Tracker

**[Live Demo](http://world-map-tracker-b478a382.s3-website-us-east-1.amazonaws.com)**

A high-performance, interactive mapping application designed for global data visualization. Built with vanilla JavaScript and Leaflet.js, this project delivers a rich spatial experience prioritizing speed and dependency minimization.

## Cloud Infrastructure & Scalability

The application is deployed on AWS using a robust, repeatable Infrastructure-as-Code (IaC) pipeline. 

* **Provisioning:** Fully automated via **Terraform** to ensure deterministic deployments and eliminate configuration drift.
* **Serverless Hosting:** Served directly via an **AWS S3 Bucket** configured for Static Website Hosting, eliminating the need for server provisioning and maintenance.
* **Auto-Scaling:** Inherently scales to handle sudden traffic spikes without requiring load balancers or auto-scaling groups.
* **Security:** Strict IAM bucket policies enforce public read-only access to assets, preventing unauthorized modifications.

## Engineering Decisions & The "Why"

* **Infrastructure-as-Code (IaC):** Adopted Terraform over manual AWS console configuration to guarantee consistent, version-controlled environments and rapid disaster recovery.
* **Zero-Maintenance Architecture:** Migrated from EC2 to S3 Static Website Hosting to drastically reduce operational costs, eliminate server patching, and improve global scalability.
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
* **Infrastructure:** AWS (S3), Terraform