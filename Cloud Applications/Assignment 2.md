# Manas Khanna - A25305223002
# Cloud Application Development and Deployment 
# CSE410
# **Dr Sachin Sharma (314937**)
## Case Study 1: PaaS Selection and Network Mitigation for Modern Web Apps

### 1. PaaS Provider Selection and Justification

**Selected Provider:** **Google App Engine (GAE)**
**Justification:**
- **Seamless REST and JSON Handling:** Google App Engine provides native, lightweight support for standard web protocols (HTTP/HTTPS) and stateless RESTful architectures. Its managed runtime environments (such as Node.js, Python, or Java) parse and serialize JSON payloads with minimal overhead, aligning directly with a JavaScript/jQuery front-end.
- **Automatic Horizontal Scaling:** Because e-learning portals experience sudden traffic spikes (e.g., exam schedules or live lectures), GAE’s automatic scaling dynamically provisions and de-provisions instances based on incoming request rates without requiring manual infrastructure intervention.
- **Zero Hardware Management & Fast Time-to-Market:** Unlike Azure App Service, which can introduce configuration complexity for straightforward web tier which faces cost scaling limits and "dyno sleeping" latency on lower tiers. GAE allows developers to deploy code directly via CLI while Google manages load balancing, OS patching, and traffic routing.
- **Global Edge Network:** Google’s private global fiber network minimizes round-trip time (RTT) for real-time interactive requests compared to Heroku (which runs atop AWS infrastructure with an added routing layer)
### 2. Potential Network Problem Areas and Mitigation Techniques

| **Problem Area**                                     | **Technical Cause**                                                                                                                                    | **Mitigation Techniques**                                                                                                                                                                                                                                                                                                                          |
| ---------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **1. High Network Latency (RTT)**                    | Frequent, small asynchronous AJAX/jQuery requests to REST APIs over long geographical distances cause noticeable UI lag during real-time interactions. | **• Content Delivery Network (CDN):** Offload static assets (JavaScript, jQuery libraries, CSS, media) to edge servers (e.g., Cloud CDN) closer to students.<br>**• API Payload Optimization:** Enable **Gzip/Brotli compression** on JSON responses and implement client-side caching (`Cache-Control` headers) to eliminate redundant API calls. |
| **2. Bandwidth Bottlenecks & Connection Exhaustion** | Concurrent student logins and simultaneous media/API requests saturate available network throughput and exhaust server connection pools.               | **• Auto-Scaling & Load Balancing:** Configure HTTP(S) Load Balancing across multiple availability zones to distribute traffic evenly.<br>**• Connection Pooling & Rate Limiting:** Implement HTTP/2 multiplexing to reuse single TCP connections for multiple JSON requests, alongside API rate limiting and pagination for large data sets.      |

## Case Study 2: Cloud Deployment Models and Automation in Enterprise

### 1. Differentiation of Cloud Deployment Models

|**Feature / Parameter**|**Public Cloud**|**Private Cloud**|**Hybrid Cloud**|**Community Cloud**|
|---|---|---|---|---|
|**Infrastructure Ownership**|Owned and operated by a third-party cloud provider (e.g., AWS, Azure).|Dedicated exclusively to a single organization (on-premises or hosted).|Combination of interconnected Private and Public clouds.|Shared by several organizations with common compliance/security goals.|
|**Tenancy**|Multi-tenant (shared hardware resources).|Single-tenant (complete physical/logical isolation).|Single-tenant for sensitive core; multi-tenant for burst workloads.|Multi-tenant restricted to a specific consortium.|
|**Security & Compliance**|Standardized security; shared responsibility model; harder to meet strict banking audits.|Maximum control over firewalls, encryption keys, and data residency; easiest regulatory compliance.|High security for core banking data kept on-premises; moderate for public tier.|High security tailored to industry-specific standards (e.g., financial consortium).|
|**Cost & Maintenance**|Low CapEx, Pay-as-you-go OpEx; zero hardware maintenance.|High CapEx/OpEx; requires dedicated internal IT staff for maintenance.|Moderate CapEx/OpEx; complex integration overhead.|Shared CapEx/OpEx among participating institutions.|
|**Suitability for FinSecure Corp**|**Low** — Data privacy and regulatory audit risks are too high for core banking systems.|**High (Optimal)** — Meets strict compliance while enabling internal developer automation.|**Moderate** — Useful if offloading non-sensitive tasks, though adds architectural complexity.|**Low** — Lack of complete autonomy over infrastructure customization.|

### 2. Key Features of Private Cloud Justifying the CTO’s Preference

- **Dedicated Single-Tenant Isolation:** Ensures that sensitive customer financial records and legacy .NET/Java APIs run on isolated compute, storage, and network hardware, eliminating "noisy neighbor" risks and preventing unauthorized cross-tenant data exposure.
- **Strict Regulatory and Governance Control:** Allows FinSecure Corp to enforce custom security policies, hardware-level encryption (HSM), granular audit logging, and strict data sovereignty rules required by banking regulations (e.g., PCI-DSS, GDPR, SOX).
- **Automated Provisioning & Self-Service Portals:** Through private cloud management platforms (such as OpenStack, VMware vRealize, or Azure Stack), developers can use a self-service catalog or Infrastructure-as-Code (IaC) APIs to spin up standardized .NET and Java testing environments on demand without waiting for manual IT ticket approvals.
- **Resource Pooling and Rapid Elasticity:** Abstracts physical servers into virtualized pools of CPU, RAM, and storage, allowing automated reclamation of testing environments once QA cycles finish.
### 3. Primary Factors Dictating Successful Deployment

1. **Network Architecture and Segmentation:** Implementing Software-Defined Networking (SDN), VLANs, and micro-segmentation to strictly isolate development/testing sandboxes from production banking environments while maintaining low-latency API communication.
2. **Orchestration and Automation Tooling:** Integrating robust Configuration Management (e.g., Ansible, Terraform) and CI/CD pipelines so that legacy .NET and Java dependencies deploy consistently across self-service environments
3. **Capacity Planning and Hardware Scalability:** Accurately forecasting peak compute and storage demands to prevent resource exhaustion when multiple developer teams spin up concurrent test environments alongside production workloads
4. **Identity, Access, and Security Governance:** Enforcing Role-Based Access Control (RBAC), Zero-Trust network policies, and automated compliance auditing across all self-service workflows so developer speed does not compromise security.
5. **Skilled Operational Workforce & TCO Management:** Ensuring internal infrastructure engineers are trained to maintain cloud orchestration software, patch hypervisors, and optimize Total Cost of Ownership (TCO) to justify the upfront capital expenditure.