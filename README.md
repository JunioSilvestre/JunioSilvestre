<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:0D1117,50:161B22,100:2EA043&height=160&section=header&text=Junio%20Silvestre&fontSize=42&fontColor=ffffff&animation=fadeIn&fontAlignY=35&desc=Linux%20Systems%20Engineer%20%C2%B7%20Cloud%20Infrastructure%20%C2%B7%20Automation&descAlignY=58&descSize=18"/>

<a href="https://github.com/JunioSilvestre">
  <img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=600&size=19&pause=1000&color=2EA043&center=true&vCenter=true&width=720&lines=Linux+Systems+Administration+%26+OS+Hardening;Bash+%26+Python+Infrastructure+Automation;Docker+Containers+%26+Kubernetes+Orchestration;Terraform+Infrastructure+as+Code+(IaC);Automated+CI%2FCD+%26+GitOps+Pipelines" alt="Typing SVG" />
</a>

<p align="center">
  <a href="mailto:jcs@jcscode.com"><img src="https://img.shields.io/badge/Email-jcs%40jcscode.com-EA4335?style=for-the-badge&logo=gmail&logoColor=white" alt="Email" /></a>
  <img src="https://img.shields.io/badge/Role-Linux_Systems_Engineer-2EA043?style=for-the-badge&logo=linux&logoColor=white" alt="Role" />
  <img src="https://img.shields.io/badge/Status-Open_to_Work-brightgreen?style=for-the-badge" alt="Open to Work" />
  <img src="https://komarev.com/ghpvc/?username=JunioSilvestre&color=2EA043&style=for-the-badge&label=PROFILE+VIEWS" alt="Profile Views" />
</p>

</div>

---

### 🎯 About Me

**Linux Systems Engineer** focused on designing, automating, and operating **reliable, security-hardened Linux and cloud-native environments**.

I combine deep hands-on **Linux systems administration** with modern DevOps engineering: automating repetitive operations with **Bash and Python**, containerizing and orchestrating workloads with **Docker and Kubernetes**, provisioning reproducible cloud infrastructure with **Terraform**, and enforcing quality through **CI/CD pipelines**.

> [!IMPORTANT]
> **Engineering Philosophy:** *"If an operation has to be done twice, script it. If it runs in production, codify it in Terraform, isolate it in containers, validate it in CI/CD, and monitor it continuously."*
>
> 📫 **Direct Contact:** [jcs@jcscode.com](mailto:jcs@jcscode.com)

<br/>

---

### 🛠️ Tech Ecosystem Overview

<div align="center">

<table>
  <tr>
    <td align="center" width="33%">
      <h4>🐧 Linux, Scripting & Networking</h4>
      <img src="https://skillicons.dev/icons?i=linux,ubuntu,debian,bash,python,nginx&perline=3" alt="Linux & Scripting" />
      <br/><br/>
      <sub><b>Ubuntu · Debian · RHEL/Rocky · Alpine<br/>GNU Bash · Python · Nginx · Tailscale</b></sub>
    </td>
    <td align="center" width="33%">
      <h4>🐳 Containers, K8s & Cloud IaC</h4>
      <img src="https://skillicons.dev/icons?i=docker,kubernetes,terraform,aws,azure,postgres&perline=3" alt="Containers & Cloud" />
      <br/><br/>
      <sub><b>Docker · Kubernetes · Helm<br/>Terraform (IaC) · AWS · Azure</b></sub>
    </td>
    <td align="center" width="33%">
      <h4>🔁 CI/CD, GitOps & Observability</h4>
      <img src="https://skillicons.dev/icons?i=githubactions,git,prometheus,grafana,redis&perline=3" alt="CI/CD & Observability" />
      <br/><br/>
      <sub><b>GitHub Actions · ArgoCD · Git<br/>Prometheus · Grafana · OpenTelemetry</b></sub>
    </td>
  </tr>
</table>

</div>

<br/>

---

### 🐧 1. Linux Systems & Bash / Python Automation

<table>
  <tr>
    <td width="50%" valign="top">
      <h4>🛡️ Linux Administration & Hardening</h4>
      <ul>
        <li><b>OS & Services:</b> Provisioning and managing Ubuntu, Debian, RHEL/Rocky, and Alpine servers; systemd units, timers, and journald diagnostics.</li>
        <li><b>Storage & Performance:</b> Filesystem management, LVM volume provisioning, memory/process inspection, and sysctl kernel tuning.</li>
        <li><b>Network & Security:</b> SSH hardening, least-privilege access/sudo policies, firewall rules (UFW / nftables / iptables), TCP/IP & DNS troubleshooting, Nginx reverse proxy, and Tailscale mesh networking.</li>
      </ul>
    </td>
    <td width="50%" valign="top">
      <h4>🐚 Bash & Python Operational Tooling</h4>
      <ul>
        <li><b>Defensive Bash Scripting:</b> Idempotent scripts for server bootstrapping, automated backups, log rotation, certificate renewal, and service auto-recovery.</li>
        <li><b>Python Automation:</b> Custom CLI utilities, REST API integrations, Cloud SDK (Boto3) resource automation, and structured log/metric parsers.</li>
        <li><b>Zero Drift:</b> Replacing manual SSH maintenance ("snowflake servers") with version-controlled, repeatable scripts and scheduled automation.</li>
      </ul>
    </td>
  </tr>
</table>

<br/>

---

### 🐳 2. Docker & Kubernetes Cluster Architecture

Rather than running monolithic workloads directly on host OS packages, I package services into **hardened, minimal Docker images** and orchestrate them on **Kubernetes** with strict isolation, self-healing probes, and observability:

```mermaid
flowchart TB
    classDef edge fill:#0D1117,stroke:#58A6FF,stroke-width:2px,color:#ffffff,font-weight:bold
    classDef k8s fill:#161B22,stroke:#326CE5,stroke-width:1.5px,color:#E6EDF3
    classDef sec fill:#161B22,stroke:#2EA043,stroke-width:1.5px,color:#E6EDF3
    classDef obs fill:#161B22,stroke:#F46800,stroke-width:1.5px,color:#E6EDF3

    Traffic(["🌐 External Traffic / TLS"]) --> Ingress["🛡️ Nginx Ingress & Rate Limiting"]:::edge

    subgraph Cluster["☸️ Kubernetes Production Cluster (Linux Worker Nodes)"]
        direction TB
        Ingress --> NetPol["🔒 RBAC · NetworkPolicies · Secrets"]:::sec
        NetPol --> Pods["🐳 Hardened Multi-Stage Docker Containers<br/>Non-Root · Liveness/Readiness Probes · HPA"]:::k8s
        Helm["📦 Helm Charts & ArgoCD GitOps"]:::k8s --> Pods
    end

    Pods --> Data["🗄️ Stateful Backing Services<br/>PostgreSQL · Redis"]:::sec
    Pods --> Monitor["📊 Observability Stack<br/>Prometheus · Grafana · OpenTelemetry"]:::obs
```

<br/>

---

### 🏗️ 3. Terraform (IaC) & Cloud Infrastructure

| Pillar | Implementation Approach | Key Focus |
|---|---|---|
| **🧱 Modular Terraform** | Reusable, parameterized Terraform modules for networking (VPC, subnets, routing), compute, IAM, and managed container clusters | Reusability & clean code |
| **🔒 Remote State & Locking** | Centralized remote state storage with state locking and strict separation between **dev**, **staging**, and **production** environments | Team safety & zero state corruption |
| **☁️ Cloud & Hybrid Ready** | Automated provisioning across **AWS** and **Azure**, combined with Linux cloud-init bootstrapping for immediate node readiness | Fast, repeatable recovery |
| **🛡️ Policy & Validation** | Automated formatting, syntax validation, and security checks before any infrastructure plan is applied | Shift-left infrastructure security |

<br/>

---

### 🔁 4. CI/CD & Automated Delivery Pipeline

Every change — whether a **Bash script**, **Python tool**, **Terraform module**, or **Dockerized service** — passes through an automated **CI/CD pipeline**:

```mermaid
flowchart LR
    classDef step fill:#161B22,stroke:#2EA043,stroke-width:1.5px,color:#E6EDF3
    classDef gate fill:#0D1117,stroke:#58A6FF,stroke-width:2px,color:#ffffff
    classDef prod fill:#2EA043,stroke:#3FB950,stroke-width:2px,color:#ffffff,font-weight:bold

    A["💻 Git Commit<br/>Bash · Python · IaC"]:::step --> B["🔍 Quality & Security Gate<br/>Lint · Test · Vulnerability Scan"]:::gate
    B --> C["🐳 Container Registry<br/>Multi-Stage Docker Build"]:::step
    B --> D["🏗️ Terraform Plan/Apply<br/>Cloud Infrastructure"]:::step
    C --> E(["🚀 Zero-Downtime Release<br/>Kubernetes & ArgoCD"]):::prod
    D --> E
```

<br/>

---

### 🏆 Certifications & Continuous Learning

<div align="center">

<a href="https://www.lpi.org/our-certifications/linux-essentials-overview">
  <img src="https://img.shields.io/badge/LPI-Linux_Essentials_(In_Progress)-FCC624?style=for-the-badge&logo=linux&logoColor=black" alt="LPI Linux Essentials" />
</a>

</div>

<br/>

---

### 📊 GitHub Activity & Metrics

<div align="center">

<img height="165em" src="https://github-profile-summary-cards.vercel.app/api/cards/profile-details?username=JunioSilvestre&theme=github_dark" alt="GitHub Profile Summary" />
<img height="165em" src="https://streak-stats.demolab.com/?user=JunioSilvestre&theme=radical&hide_border=true&background=0D1117&stroke=2EA043&ring=2EA043&fire=2EA043&currStreakLabel=2EA043" alt="GitHub Streak" />

</div>

<br/>

---

### 💼 Open to Opportunities

<div align="center">

<p>
  I am open to <strong>Linux Systems Engineer · Infrastructure Engineer · DevOps / SRE</strong> roles where Linux reliability, Bash/Python automation, Terraform (IaC), and Kubernetes orchestration are core to the engineering culture.
</p>

<p>
  <a href="mailto:jcs@jcscode.com"><img src="https://img.shields.io/badge/Contact_Me-jcs%40jcscode.com-EA4335?style=for-the-badge&logo=gmail&logoColor=white" alt="Contact Me" /></a>
</p>

</div>

<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:2EA043,50:161B22,100:0D1117&height=80&section=footer" width="100%"/>

</div>
