# Secure-Software-Development-note-DevSecOps
Here are my notes after completing tryhackme secure software development module
# Introduction to DevSecOps & SDLC Methodologies

## Introduction to DevSecOps

**DevOps** (Developer Operations) transforms development infrastructure into a fully automated, self-service ecosystem.

* Developers can provision resources to public clouds independently, without relying on IT.
* Continuous Integration and Continuous Deployment (CI/CD) automatically sets up testing, staging, and production environments.
* **Infrastructure as Code (IaC):** Tools like Terraform and Vagrant are widely used to deploy environments declaratively.
* Organizations dynamically provision containerized workloads using adaptive processes.

### Core DevOps Tools and Processes

* **CI/CD:** Focuses on frequently merging code and integrating automated testing to perform continuous checks on new code pushes.
* **Infrastructure as Code (IaC):** Managing and provisioning infrastructure through reusable code and automation.
* **Configuration Management:** Managing the state of infrastructure constantly and applying changes efficiently for better maintainability.
* **Orchestration:** The automation of complex workflows to achieve system stability.
* **Monitoring:** Collecting data on the performance and stability of services and infrastructure.
* **Microservices:** An architectural approach that breaks an application into many small, independent services.

### DevSecOps & "Shifting Left"

* **The Old Way:** Security testing was implemented at the very end of the development cycle.
* **Shifting Left:** Integrating security measures during *all* stages of the development cycle, from the very beginning. This approach in DevOps is explicitly referred to as **DevSecOps**.

### DevSecOps Challenges

* **Security Silos:** Treating security and DevOps as separate entities prevents engineers from understanding or applying security measures effectively.
* **Lack of Visibility:** The goal is to create a culture where security is treated as a standard, visible aspect of application development, not an afterthought.
* **Stringent Processes:** Security compliance verification must not become a complicated, innovation-blocking bottleneck for every new piece of software.

---

## SDLC (Software Development Life Cycle)

SDLC is a framework and set of practices standardizing the process of building software applications by splitting tasks into distinct phases.

### The 7 Phases of SDLC

1. **Planning:** Project and product management (resource allocation, scheduling, cost estimation).
2. **Requirements Definition:** Determining exactly what the application must do and establishing requirements.
3. **Design and Prototyping:** Establishing architecture, programming languages, and component communication.
4. **Software Development:** The actual coding, program building, and documentation.
5. **Testing:** Ensuring components work correctly and interact securely.
6. **Deployment:** Releasing the software to a live environment.
7. **Operations and Maintenance:** Responding to bugs, flaws, user issues, and planning additional features.

### DevOps Metrics

* **Meantime to Production (MTTP):** The turnaround time for newly committed source code.
* **Frequency of Deployment:** How often new releases are pushed.
* **Average Lead Time:** The total time to develop, build, test, and deploy a new feature.
* **Speed of Deployment:** The time it takes a release to deploy into production once initiated.
* **Deployment Agility:** A combination of deployment speed and frequency.
* **Production Failure Rate:** How often failures occur in the live production environment.
* **Mean Time to Recover (MTTR):** The recovery time required after a failure occurs.

> **Brooks's Law:** *"Adding human resources to a late software project will make it later."* Adding developers decreases the efficacy of sprints due to onboarding and communication overhead.

---

## S-SDLC (Secure Software Development Life Cycle)

Traditional SDLC introduces security too late, making vulnerability remediation highly expensive. S-SDLC integrates security continuously.

### Establishing a Security Posture

1. **Perform a Gap Analysis:** Determine existing activities/policies and evaluate their effectiveness.
2. **Create Software Security Initiatives (SSI):** Establish realistic goals with defined metrics for success.
3. **Formalize Processes:** Standardize security activities within your SSI.
4. **Invest:** Allocate resources for engineer security training and appropriate tools.

### S-SDLC Core Processes

1. **Risk Assessment (Early Stage):** Identify security considerations during the Planning and Requirements stages to promote a "Security by Design" approach.
2. **Threat Modeling:** Identifying potential threats against the system architecture.
3. **Code Scanning/Review:** Automated and manual analysis of source code.
4. **Security Assessments:** Penetration testing and vulnerability assessments.

---

## Risk Assessment & Threat Modeling

### Performing a Risk Assessment

1. **Assume Compromise:** Assume the software *will* be attacked and analyze threat actor motivations.
2. **Risk Evaluation:** Consider worst-case scenarios and the impact of a successful attack.
3. **Target Accessibility:** Determine how the system is accessed (local vs. network, authenticated vs. unauthenticated).

**Types of Risk Assessment:**

* **Qualitative:** Assesses risk into thresholds (Low, Medium, High). *Formula: Risk = Severity x Likelihood.*
* **Quantitative:** Uses hard numbers and calculations to represent risk bands based on company processes.

### Threat Modeling Frameworks

**1. STRIDE (What could go wrong?)**

* **S**poofing: Impersonation violating authentication (e.g., ARP, IP, DNS spoofing).
* **T**ampering: Unauthorized data modification violating integrity.
* **R**epudiation: Lack of accountability violating non-repudiability.
* **I**nformation Disclosure: Data breaches violating confidentiality.
* **D**enial of Service: Exhaustion of resources violating availability.
* **E**levation of Privilege: Escalating access rights violating authorization.

**2. DREAD (Risk Probability Rating)**
Scored on a scale of 0–10:

* **D**amage: The potential impact.
* **R**eproducibility: The complexity of reproducing the threat.
* **E**xploitability: How easily it can be exploited.
* **A**ffected Users: The volume of users impacted.
* **D**iscoverability: How easy the threat is to find.

**3. PASTA (Process for Attack Simulation and Threat Analysis)**
Aligns technical requirements with business objectives across 7 stages:

1. Define Objectives
2. Define Technical Scope
3. Decomposition & Analysis
4. Threat Analysis
5. Vulnerabilities & Weaknesses Analysis
6. Attack/Exploit Enumeration & Modelling
7. Risk Impact Analysis

---

## Code Analysis & Security Testing

* **SAST (Static Application Security Testing):** White-box testing analyzing source code *before* the app is live/running.
* **DAST (Dynamic Application Security Testing):** Black-box testing detecting vulnerabilities inside a running, deployed web application.
* **IAST (Interactive Application Security Testing):** Grey-box testing deployed side-by-side with the main application on the server.
* **Vulnerability Assessments:** Automated tools (OpenVAS, Nessus) find vulnerabilities but *do not* validate or exploit them.
* **Penetration Testing:** Goes deeper by manually validating vulnerabilities, quantifying real-world risk, and attempting to penetrate the system.

---

## SDLC Security Methodologies

Prominent methodologies include Microsoft's SDL, OWASP's S-SDLC, and Software Security Touchpoints.

### Microsoft Security Development Lifecycle (SDL) Principles

* **Secure by Design:** Security is a built-in quality attribute affecting the entire lifecycle.
* **Secure by Default:** Software is constructed to minimize harm (e.g., deployed with least privilege).
* **Secure in Deployment:** Deployment is accompanied by tools and guidance for admins.
* **Communications:** Open and timely communication regarding occurring threats.

### Implementing SDL Practices (The 11 Steps)

1. Provide comprehensive training.
2. Define exact security requirements.
3. Define metrics and compliance reporting.
4. Perform Threat Modeling.
5. Establish design requirements.
6. Define and strictly use cryptography standards.
7. Manage the security risks of third-party components.
8. Use officially approved tools.
9. Perform Security Testing (SAST, DAST, IAST).
10. Perform Security Assessments (Pentesting).
11. Establish a standard incident response process.

### Core S-SDLC Principles

* Mandatory security activities are grouped by traditional SDLC phases.
* Data is collected to assess training effectiveness.
* In-process metrics confirm compliance; post-release metrics guide future changes.
* Heavy emphasis is placed on understanding the *cause and effect* of security vulnerabilities.
* *(Note: A development team must complete 16 mandatory security activities to comply strictly with the Microsoft SDL process).*
