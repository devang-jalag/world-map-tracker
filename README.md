# World Map Tracker

**[Live Demo](http://52.91.57.20)**

A high-performance, interactive mapping application designed for global data visualization. Built with vanilla JavaScript and Leaflet.js, this project delivers a rich spatial experience prioritizing speed and dependency minimization.

## Cloud Infrastructure & Scalability

The application is deployed on AWS using a robust, repeatable Infrastructure-as-Code (IaC) pipeline. 

* **Provisioning:** Fully automated via **Terraform** to ensure deterministic deployments and eliminate configuration drift.
* **Network Isolation:** Resources reside within a custom VPC, utilizing dedicated subnets, route tables, and an Internet Gateway to tightly control traffic flow.
* **Web Tier:** Served by an Nginx web server on a dedicated Ubuntu EC2 instance, bootstrapped automatically using cloud-init `user_data` scripts.
* **Security:** AWS Security Groups strictly restrict ingress to HTTP (Port 80) and SSH (Port 22), blocking unauthorized access.

## Engineering Decisions & The "Why"

* **Infrastructure-as-Code (IaC):** Adopted Terraform over manual AWS console configuration to guarantee consistent, version-controlled environments and rapid disaster recovery.
* **Zero-Dependency Core Logic:** Chosen vanilla JavaScript over heavy frontend frameworks to maximize render performance for dynamic map objects and reduce time-to-interactive.
* **Open-Source Mapping:** Leveraged Leaflet.js with OpenStreetMap tile layers to bypass vendor lock-in and avoid the restrictive rate limits and high costs associated with proprietary mapping APIs.
* **Automated Bootstrapping:** Implemented cloud-init scripts to autonomously pull the latest repository state and configure Nginx on boot, removing the need for manual server configuration.

## Repository Structure

```text
.
├── map-infra/                 # Infrastructure as Code
│   ├── main.tf                # Terraform configuration (VPC, EC2, Networking)
│   └── .terraform.lock.hcl    # Terraform dependency lockfile
├── index.html                 # Main application entry point & UI
└── README.md                  # Project documentation
```

## Tech Stack
* **Frontend:** Vanilla JavaScript, HTML5, CSS3, Leaflet.js
* **Mapping:** OpenStreetMap
* **Infrastructure:** AWS (EC2, VPC, Security Groups), Terraform
* **Web Server:** Nginx (Ubuntu Linux)