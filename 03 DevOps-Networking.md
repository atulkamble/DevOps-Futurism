# 🌐 DevOps Networking Complete Guide

**(Concepts • Architectures • Commands • Interview Ready)**

![Networking Overview](https://substackcdn.com/image/fetch/%24s_%21F636%21%2Cf_auto%2Cq_auto%3Agood%2Cfl_progressive%3Asteep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fa29b682c-cff6-4ed3-a085-4347eb020b06_1906x1150.png)

![TCP/IP Model](https://afteracademy.com/images/what-is-the-tcp-ip-model-and-how-it-works-tcp-ip-model-five-layers-195bdaa7116cd850.jpg)

![OSI Model](https://cdn2.hubspot.net/hubfs/2954816/The%207%20Layers%20of%20OSI.png)

---

## 📚 Table of Contents
1. [Fundamental Concepts](#1-fundamental-networking-concepts)
2. [DevOps-Specific Topics](#2-devops-specific-networking)
3. [Architecture Patterns](#3-networking-architectures)
4. [Ports & Protocols Reference](#4-ports-protocols-reference)
5. [Commands & Troubleshooting](#5-commands-troubleshooting)
6. [Interview Tips](#6-interview-tips)

---

## 1️⃣ Fundamental Networking Concepts

### 🔹 What is a Network?

A **network** is a collection of computers/devices connected to share **data, resources, and services**.

**DevOps Context:**
* CI/CD tools communicate with Git, registries, cloud APIs
* Containers & VMs communicate over networks
* Monitoring & logging depend on network access

**Key Points:**
* Everything in DevOps communicates over a network
* Network failure = pipeline failure

### 🔹 Network Types

| Type | Definition | DevOps Example |
|------|------------|----------------|
| LAN | Local Area Network | Office / Data Center |
| WAN | Wide Area Network | Internet |
| VPC/VNet | Cloud private network | AWS VPC / Azure VNet |
| Overlay | Virtual network over physical | Kubernetes, Docker |

### 🔹 OSI & TCP/IP Models

![OSI vs TCP/IP](https://docs.oracle.com/cd/E26505_01/html/E27061/figures/ipov.fig88.png)

**OSI (7 Layers):** Physical → Data Link → Network → Transport → Session → Presentation → Application

**TCP/IP (4 Layers):** Network Access → Internet → Transport → Application

**DevOps Mapping:**
* HTTP/HTTPS → Application Layer
* TCP/UDP → Transport Layer  
* IP → Network Layer

**Remember:** Most DevOps issues occur at Layer 4-7

### 🔹 IP Addressing & CIDR

**IPv4 Format:** `192.168.1.10`

**Private IP Ranges:**
* `10.0.0.0/8` (16.7M addresses)
* `172.16.0.0/12` (1M addresses) 
* `192.168.0.0/16` (65K addresses)

**CIDR Examples:**
* `/24` = 256 IPs
* `/16` = 65,536 IPs
* `/8` = 16.7M IPs

**DevOps Usage:**
* VPC/Subnet design
* Kubernetes Pod IP planning
* Avoiding IP conflicts

### 🔹 DNS (Domain Name System)

**Function:** Translates domain names → IP addresses

Example: `api.example.com` → `192.168.1.100`

**DevOps Scenarios:**
* Load balancer configuration
* Service discovery in Kubernetes
* Blue-Green deployments
* Failover routing

### 🔹 NAT (Network Address Translation)

**Purpose:** Allows private IPs to access internet via public IP

**DevOps Usage:**
* Private EC2/VM updates
* Kubernetes node outbound traffic
* Cost optimization (saves public IPs)

---

## 2️⃣ DevOps-Specific Networking

### 🔹 Container Networking (Docker)

![Docker Networking](https://media2.dev.to/dynamic/image/width%3D1000%2Cheight%3D420%2Cfit%3Dcover%2Cgravity%3Dauto%2Cformat%3Dauto/https%3A%2F%2Fdev-to-uploads.s3.amazonaws.com%2Fuploads%2Farticles%2Fiqcp0sjzh8mgaocznkx9.png)

**Network Types:**
* **Bridge** (default): Container-to-container on same host
* **Host**: Container uses host's network stack
* **Overlay**: Multi-host container communication
* **None**: No networking

**Key Concepts:**
* Each container gets internal IP
* Port mapping exposes services: `-p 8080:80`
* Containers communicate via container names

### 🔹 Kubernetes Networking

![K8s Networking](https://opensource.com/sites/default/files/2022-05/1containerandpodnets.jpg)

**Core Principles:**
* Every Pod gets unique IP
* Pod-to-Pod communication without NAT
* Flat network model

**Service Types:**
* **ClusterIP**: Internal cluster communication
* **NodePort**: External access via node ports (30000-32767)
* **LoadBalancer**: Cloud provider load balancer
* **Ingress**: HTTP/HTTPS routing

**CNI Plugins:** Calico, Flannel, Cilium, Weave

### 🔹 Load Balancing

![Load Balancer Types](https://journaldev.nyc3.cdn.digitaloceanspaces.com/2019/03/nginx-reverse-proxy.png)

**Layer 4 (L4):** TCP/UDP load balancing (fast, connection-based)
**Layer 7 (L7):** HTTP/HTTPS load balancing (content-aware routing)

**Popular Tools:**
* NGINX
* HAProxy  
* Cloud LB (AWS ALB/NLB, Azure Load Balancer)

**DevOps Usage:**
* High availability
* Traffic distribution
* Health checks
* Blue-Green deployments

### 🔹 Security: Firewalls & Security Groups

**Layers:**
* **Host Firewall**: iptables, ufw
* **Cloud Security Groups**: AWS SG, Azure NSG
* **Network ACLs**: Subnet-level rules
* **Application Firewall**: WAF

**Best Practices:**
* Default deny approach
* Least privilege principle
* Regular rule audits

---

## 3️⃣ Networking Architectures

### 🔹 Client-Server Architecture
```
[Client] ──HTTP/HTTPS──> [Server]
(Browser)                (API/App)
```

### 🔹 Three-Tier Architecture
```
[Presentation Tier] ──> Nginx/Apache (Port 80/443)
        ↓
[Application Tier]  ──> Backend App (Port 8080)
        ↓
[Data Tier]        ──> Database (Port 3306/5432)
```

### 🔹 Cloud VPC Architecture

![VPC Architecture](https://docs.aws.amazon.com/images/vpc/latest/userguide/images/how-it-works.png)

```
VPC (10.0.0.0/16)
├── Public Subnet (10.0.1.0/24)
│   └── Load Balancer, Bastion Host
├── Private Subnet (10.0.2.0/24)
│   └── Application Servers
└── DB Subnet (10.0.3.0/24)
    └── Databases
```

### 🔹 Kubernetes Architecture
```
[Internet] → [Ingress Controller] → [Service] → [Pods]
                                       ↓
                               [ConfigMap/Secret]
```

### 🔹 CI/CD Network Flow
```
Developer → Git Repo → CI Server → Registry → K8s/VM
    ↓           ↓          ↓           ↓         ↓
   SSH       Webhook    API Calls   Push    Deploy
```

---

## 4️⃣ Ports & Protocols Reference

### 🌐 Core Networking Ports

| Port | Protocol | Service | DevOps Usage |
|------|----------|---------|--------------|
| 22 | TCP | SSH | Server access, Git over SSH |
| 53 | TCP/UDP | DNS | Service discovery, resolution |
| 80 | TCP | HTTP | Web apps, load balancers |
| 443 | TCP | HTTPS | Secure APIs, endpoints |
| 123 | UDP | NTP | Time synchronization |

### 🔐 Security & Authentication

| Port | Protocol | Service | Usage |
|------|----------|---------|--------|
| 389 | TCP/UDP | LDAP | Identity services |
| 636 | TCP | LDAPS | Secure LDAP |
| 88 | TCP/UDP | Kerberos | Enterprise auth |
| 1812 | UDP | RADIUS | VPN authentication |

### 📦 DevOps Tools

| Port | Tool | Usage |
|------|------|--------|
| 8080 | Jenkins | CI server UI |
| 9000 | SonarQube | Code quality |
| 3000 | Grafana | Monitoring dashboards |
| 9090 | Prometheus | Metrics collection |
| 5601 | Kibana | Log visualization |

### 🐳 Container & Orchestration

| Port | Component | Purpose |
|------|-----------|---------|
| 2376 | Docker Daemon | Secure Docker API |
| 6443 | Kubernetes API | Cluster management |
| 10250 | Kubelet | Node agent |
| 30000-32767 | NodePort | External access |

### ☁️ Databases & Storage

| Port | Service | Usage |
|------|---------|-------|
| 3306 | MySQL | Relational database |
| 5432 | PostgreSQL | Advanced relational DB |
| 27017 | MongoDB | NoSQL database |
| 6379 | Redis | In-memory cache |
| 9200 | Elasticsearch | Search engine |

### 📊 Monitoring & Messaging

| Port | Tool | Purpose |
|------|------|---------|
| 9100 | Node Exporter | System metrics |
| 5672 | RabbitMQ | Message broker |
| 9092 | Kafka | Event streaming |
| 5044 | Logstash | Log processing |

---

## 5️⃣ Commands & Troubleshooting

### 🔹 Network Inspection

```bash
# Basic network info
ip a                    # Show IP addresses
ip route               # Display routing table
hostname -I            # Get host IP address
cat /etc/hosts         # Local DNS mappings
cat /etc/resolv.conf   # DNS servers
```

### 🔹 Connectivity Testing

```bash
# Reachability tests
ping google.com                # Basic connectivity
ping -c 5 8.8.8.8             # Limited pings
traceroute google.com         # Network path
mtr google.com                # Combined ping/traceroute
```

### 🔹 DNS Resolution

```bash
# DNS debugging
nslookup google.com           # Basic DNS lookup
dig google.com                # Advanced DNS query
dig +short google.com         # IP only
host google.com               # Simple lookup
```

### 🔹 Port & Service Debugging

```bash
# Port analysis
ss -tulnp                     # List listening ports (modern)
netstat -tulnp               # List ports (legacy)
lsof -i :8080                # Who's using port 8080
lsof -i tcp:443              # HTTPS connections
```

### 🔹 HTTP/API Testing

```bash
# Web service testing
curl https://api.example.com
curl -I https://example.com          # Headers only
curl -v https://example.com          # Verbose output
curl -X POST -d '{}' https://api.com # POST request
wget https://example.com/file.zip    # Download files
```

### 🔹 Firewall Management

```bash
# Linux firewalls
iptables -L -n            # List iptables rules
ufw status                # Ubuntu firewall status
ufw allow 8080            # Allow port
firewall-cmd --list-all   # CentOS/RHEL firewall
```

### 🔹 Container Networking

```bash
# Docker networking
docker network ls                    # List networks
docker network inspect bridge       # Inspect network
docker port container_name          # Port mappings
docker exec -it container ping host # Test from container
```

### 🔹 Kubernetes Networking

```bash
# K8s network debugging
kubectl get nodes -o wide            # Node IPs
kubectl get pods -o wide             # Pod IPs
kubectl get svc                      # Services
kubectl describe svc service-name    # Service details
kubectl port-forward pod/name 8080:80 # Port forwarding
```

### 🔹 Advanced Debugging

```bash
# Packet capture
tcpdump -i eth0                      # Capture all traffic
tcpdump -i eth0 port 80              # HTTP traffic only
tcpdump -i eth0 host 192.168.1.10   # Specific host

# Network performance
iperf3 -s                            # Start server
iperf3 -c server-ip                  # Test bandwidth
```

### 🔹 Troubleshooting Workflow

```text
1. DNS Issue?     → dig / nslookup
2. Port Open?     → ss / lsof
3. Service Up?    → systemctl status
4. HTTP Issue?    → curl -v
5. Network Path?  → traceroute / mtr
6. Packet Loss?   → tcpdump
7. K8s Issue?     → kubectl describe
```

### 🔹 Essential Commands Checklist

```bash
# Top 15 must-know commands
ip a                 # Network interfaces
ip route            # Routing table  
ping                # Connectivity
traceroute          # Network path
mtr                 # Combined ping/trace
dig                 # DNS queries
ss -tulnp          # Listening ports
lsof -i            # Network connections
curl -v            # HTTP testing
kubectl get svc    # K8s services
docker network ls  # Docker networks
tcpdump            # Packet capture
iptables -L        # Firewall rules
netstat -r         # Routing (legacy)
nslookup           # DNS lookup
```

---

## 6️⃣ Interview Tips

### 🎯 Key Interview Topics

| Topic | Must Know |
|-------|-----------|
| **Basics** | IP, CIDR, DNS, ports |
| **Cloud** | VPC, subnets, security groups |
| **Containers** | Docker bridge, overlay networks |
| **Kubernetes** | Pods, Services, Ingress |
| **DevOps** | CI/CD networking, troubleshooting |

### 🧠 Common Interview Questions

**Q: Explain Kubernetes networking**
A: "Every Pod gets its own IP address. Pods communicate directly without NAT. Services provide stable endpoints for Pod groups. Ingress handles external HTTP traffic."

**Q: Docker vs Kubernetes networking?**
A: "Docker uses bridge networks by default with NAT. Kubernetes uses flat networking where every Pod can reach every other Pod directly."

**Q: How do you troubleshoot network issues?**
A: "Start with basic connectivity (ping), check DNS resolution (dig), verify ports (ss), test HTTP endpoints (curl), and analyze packets if needed (tcpdump)."

### 📝 Interview One-Liners

* "Security Groups are stateful, NACLs are stateless"
* "Every Pod has its own IP in Kubernetes"
* "Ingress works at Layer 7, LoadBalancer at Layer 4"
* "Use `ss` instead of `netstat` - it's more efficient"
* "Docker bridge uses NAT, Kubernetes doesn't"

### ✅ Golden Rules

1. **Everything** in DevOps communicates over network
2. **Understand** IP addressing, ports, DNS, and CIDR
3. **Cloud networking** is software-defined
4. **Kubernetes networking** is mandatory knowledge
5. **Security** starts at the network level
6. **Always test** from source to destination
7. **Use modern tools**: `ip` over `ifconfig`, `ss` over `netstat`

---

## 🔧 Common Issues & Solutions

| Issue | Cause | Solution |
|-------|-------|----------|
| Pod unreachable | CNI misconfiguration | Check CNI plugin, node networking |
| Service not accessible | Wrong service type | Use LoadBalancer for external access |
| CI job fails | Firewall/proxy blocking | Check security groups, proxy settings |
| App latency | DNS/load balancer delay | Optimize DNS TTL, check LB health |
| HTTPS errors | Certificate/TLS issues | Verify certificates, check TLS versions |

---

**🎯 Remember**: Networking is the foundation of DevOps. Master these concepts, practice the commands, and you'll be ready for both interviews and production troubleshooting!