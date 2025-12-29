## 🌐 DevOps Networking Prerequisites

![Image](https://substackcdn.com/image/fetch/%24s_%21F636%21%2Cf_auto%2Cq_auto%3Agood%2Cfl_progressive%3Asteep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fa29b682c-cff6-4ed3-a085-4347eb020b06_1906x1150.png)

## 🌐 Internet – Server – Client 

![Image](https://substackcdn.com/image/fetch/%24s_%21g3db%21%2Cf_auto%2Cq_auto%3Agood%2Cfl_progressive%3Asteep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F4a38175b-11e8-40ae-879c-ab3ce2027089_2008x1252.png)

![Image](https://i0.wp.com/www.ewebguru.com/web-hosting-blog/wp-content/uploads/2020/01/What-is-a-Web-Server.jpg?resize=800%2C538\&ssl=1)

### 🔹 What is the **Internet**?

The **Internet** is a global network of interconnected computers and servers that communicate using standard protocols (TCP/IP).

👉 Think of it as a **highway** that connects millions of servers and clients worldwide.

---

### 🔹 What is a **Client**?

A **client** is any device or application that **requests** data or services.

**Examples:**

* Web browser (Chrome, Firefox)
* Mobile apps
* `curl`, `Postman`
* Laptop, phone, tablet

📌 Client role:

* Sends **request**
* Receives **response**
* Does NOT usually store or process large data

---

### 🔹 What is a **Server**?

A **server** is a machine or service that **provides** data or functionality to clients.

**Examples:**

* Web server (Apache, Nginx)
* Application server (Node.js, Java, .NET)
* Database server (MySQL, PostgreSQL)

📌 Server role:

* Listens on a **port**
* Processes requests
* Sends responses
* Runs 24×7

---

### 🔁 How Client–Server Communication Works

```
Client (Browser)
   |
   |  HTTP/HTTPS Request
   v
Internet (DNS + Routing)
   |
   v
Server (Web/App Server)
   |
   |  HTTP/HTTPS Response
   v
Client (HTML / JSON / Data)
```

**Step-by-step:**

1. Client enters a URL (e.g., `www.example.com`)
2. DNS converts domain → IP address
3. Client sends request to server IP & port
4. Server processes request
5. Server sends response
6. Client displays result

---

### 🔹 Common Protocols Used

| Protocol     | Purpose                   |
| ------------ | ------------------------- |
| HTTP / HTTPS | Web communication         |
| TCP          | Reliable data transfer    |
| UDP          | Fast, connectionless data |
| FTP / SFTP   | File transfer             |
| SMTP         | Email sending             |
| DNS          | Name resolution           |

---

### 🔹 Common Ports

| Service | Port |
| ------- | ---- |
| HTTP    | 80   |
| HTTPS   | 443  |
| SSH     | 22   |
| FTP     | 21   |
| DNS     | 53   |

---

### 🔹 Real-World Example

📱 You open **google.com**:

* **Client**: Your browser
* **Internet**: ISP + DNS + routers
* **Server**: Google web servers
* **Response**: Web page content

---

### 🔹 Why This is Important for DevOps 🚀

* CI/CD pipelines talk to servers
* Kubernetes pods are clients & servers
* Load balancers sit between clients & servers
* Cloud apps are fully client-server based

---

## 🌐 OSI Model vs TCP/IP Model (Tabular Comparison)

![Image](https://bluecatnetworks.com/wp-content/uploads/2022/08/The-7-layers-of-the-OSI-model_rev1-1.jpg)

![Image](https://docs.oracle.com/cd/E26505_01/html/E27061/figures/ipov.fig88.png)

![Image](https://www.networkstraining.com/wp-content/uploads/2022/09/osi-tcpip.png)

| **Feature**                       | **OSI Model**                                                               | **TCP/IP Model**                                  |
| --------------------------------- | --------------------------------------------------------------------------- | ------------------------------------------------- |
| **Full Form**                     | Open Systems Interconnection                                                | Transmission Control Protocol / Internet Protocol |
| **Developed By**                  | ISO (International Organization for Standardization)                        | DARPA (US Department of Defense)                  |
| **Number of Layers**              | **7 Layers**                                                                | **4 Layers**                                      |
| **Layer Names**                   | Application, Presentation, Session, Transport, Network, Data Link, Physical | Application, Transport, Internet, Network Access  |
| **Concept vs Practical**          | Conceptual / Reference model                                                | Practical / Implemented model                     |
| **Protocol Dependency**           | Protocol-independent                                                        | Protocol-dependent                                |
| **Layer Separation**              | Very strict separation of layers                                            | Less strict; some layers are combined             |
| **Session & Presentation Layers** | Separate layers exist                                                       | Included in Application layer                     |
| **Network Layer**                 | Supports both connection-oriented & connectionless services                 | Supports only connectionless (IP)                 |
| **Transport Layer**               | No specific protocol defined                                                | Uses TCP (reliable) & UDP (unreliable)            |
| **Error Handling**                | Data Link & Transport layers                                                | Transport layer                                   |
| **Usage**                         | Used for learning, teaching, and understanding networking                   | Used in real-world networking & Internet          |
| **Example Protocols**             | Conceptual only                                                             | HTTP, HTTPS, FTP, TCP, UDP, IP, ICMP              |

---

## 🧠 Layer Mapping (OSI → TCP/IP)

| **OSI Layer** | **TCP/IP Layer** |
| ------------- | ---------------- |
| Application   | Application      |
| Presentation  | Application      |
| Session       | Application      |
| Transport     | Transport        |
| Network       | Internet         |
| Data Link     | Network Access   |
| Physical      | Network Access   |

---

![Image](https://afteracademy.com/images/what-is-the-tcp-ip-model-and-how-it-works-tcp-ip-model-five-layers-195bdaa7116cd850.jpg)

![Image](https://cdn2.hubspot.net/hubfs/2954816/The%207%20Layers%20of%20OSI.png)

![Image](https://docs.aws.amazon.com/images/vpc/latest/userguide/images/how-it-works.png)

![Image](https://cloudnativenow.com/wp-content/uploads/2023/12/Screenshot-2023-12-03-at-8.53.56-PM.png)

---

## 1️⃣ Basics of Computer Networking

### 🔹 What is a Network?

A **network** is a collection of computers/devices connected to share **data, resources, and services**.

**DevOps Context**

* CI/CD tools talk to Git, registries, cloud APIs
* Containers & VMs communicate over networks
* Monitoring & logging depend on network access

**Points to Remember**

* Everything in DevOps communicates over a network
* Network failure = pipeline failure

---

## 2️⃣ Types of Networks

| Network         | Definition                    | DevOps Example       |
| --------------- | ----------------------------- | -------------------- |
| LAN             | Local Area Network            | Office / Data Center |
| WAN             | Wide Area Network             | Internet             |
| VPC/VNet        | Cloud private network         | AWS VPC / Azure VNet |
| Overlay Network | Virtual network over physical | Kubernetes, Docker   |

**Points to Remember**

* Cloud networks are **software-defined**
* Kubernetes uses **overlay networking**

---

## 3️⃣ IP Addressing

### 🔹 IP Address

A **unique identifier** for a device on a network.

* IPv4 → `192.168.1.10`
* IPv6 → `2001:db8::1`

### 🔹 Private IP Ranges (Important)

* `10.0.0.0/8`
* `172.16.0.0/12`
* `192.168.0.0/16`

**DevOps Usage**

* VMs, Pods, Containers use private IPs
* Public IPs expose services to users

**Points to Remember**

* Private IP ≠ Internet accessible
* Public IP = billable + security risk

---

## 4️⃣ CIDR (Classless Inter-Domain Routing)

### 🔹 CIDR Notation

Defines **IP range + subnet size**

Example:

* `10.0.0.0/24` → 256 IPs
* `10.0.0.0/16` → 65,536 IPs

**DevOps Usage**

* VPC/Subnet design
* Kubernetes Pod IP planning

**Points to Remember**

* Smaller `/` → larger network
* Bad CIDR planning breaks scaling

---

## 5️⃣ OSI & TCP/IP Models

### 🔹 OSI Model (7 Layers)

1. Physical
2. Data Link
3. Network
4. Transport
5. Session
6. Presentation
7. Application

### 🔹 TCP/IP Model (4 Layers)

* Application
* Transport
* Internet
* Network Access

**DevOps Mapping**

* HTTP → Application
* TCP/UDP → Transport
* IP → Network

**Points to Remember**

* Troubleshooting follows layers
* Most DevOps issues = Layer 4–7

---

## 6️⃣ Protocols (Must-Know)

| Protocol   | Port | Usage                |
| ---------- | ---- | -------------------- |
| HTTP       | 80   | Web traffic          |
| HTTPS      | 443  | Secure web           |
| SSH        | 22   | Server access        |
| FTP        | 21   | File transfer        |
| SFTP       | 22   | Secure file transfer |
| DNS        | 53   | Name resolution      |
| SMTP       | 25   | Email                |
| MySQL      | 3306 | Database             |
| PostgreSQL | 5432 | Database             |

**Points to Remember**

* Security Groups & Firewalls work on **ports**
* Wrong port = service unreachable

---

## 7️⃣ DNS (Domain Name System)

### 🔹 What is DNS?

Translates **domain names → IP addresses**

Example:

```
google.com → 142.250.x.x
```

**DevOps Usage**

* Load balancers
* Kubernetes services
* Cloud applications

**Points to Remember**

* DNS issues look like “application down”
* TTL affects deployment rollouts

---

## 8️⃣ NAT (Network Address Translation)

### 🔹 What is NAT?

Allows **private IPs** to access the **internet** using a public IP.

**DevOps Usage**

* Private EC2/VM updates
* Kubernetes node outbound traffic

**Points to Remember**

* Inbound ❌ | Outbound ✅
* Saves public IP cost

---

## 9️⃣ Firewalls & Security Groups

### 🔹 Firewall

Controls **inbound & outbound traffic**

* OS firewall (iptables, ufw)
* Cloud firewall (Security Groups, NSG)

**DevOps Usage**

* Protect servers, containers, clusters

**Points to Remember**

* Default deny is safest
* Least privilege networking

---

## 🔟 Load Balancing

### 🔹 What is Load Balancer?

Distributes traffic across multiple servers.

**Types**

* L4 (TCP/UDP)
* L7 (HTTP/HTTPS)

**DevOps Usage**

* Kubernetes Ingress
* Cloud ALB / NLB

**Points to Remember**

* Enables high availability
* Health checks are critical

---

## 1️⃣1️⃣ Kubernetes Networking (DevOps Critical)

### 🔹 Key Concepts

* Pod has its own IP
* Pod-to-Pod communication without NAT
* Services provide stable IP/DNS

**Points to Remember**

* Cluster networking is flat
* CNI plugin is mandatory

---

## 1️⃣2️⃣ Networking Troubleshooting Commands

| Command            | Purpose            |
| ------------------ | ------------------ |
| `ping`             | Connectivity check |
| `curl`             | API / service test |
| `netstat` / `ss`   | Open ports         |
| `traceroute`       | Path check         |
| `nslookup` / `dig` | DNS check          |
| `iptables -L`      | Firewall rules     |

**Points to Remember**

* Always test from source → destination
* Logs + network go together

---

## ✅ Final DevOps Networking Golden Rules

✔ Everything communicates over network
✔ Understand IP, ports, DNS, CIDR clearly
✔ Cloud networking is software-defined
✔ Kubernetes networking is mandatory skill
✔ Security starts at network level

---


## 🌐 **Core Networking & System Ports**

| Port | Protocol | Service | DevOps Usage                            |
| ---- | -------- | ------- | --------------------------------------- |
| 22   | TCP      | SSH     | Server access, Git over SSH, automation |
| 23   | TCP      | Telnet  | ❌ Legacy (avoid)                        |
| 53   | TCP/UDP  | DNS     | Service discovery, cluster resolution   |
| 80   | TCP      | HTTP    | Web apps, ALB/Ingress                   |
| 443  | TCP      | HTTPS   | Secure APIs, CI/CD endpoints            |
| 123  | UDP      | NTP     | Time sync (certs, logs, auth)           |

---

## 🔐 **Security & Authentication**

| Port | Protocol | Service     | Usage                     |
| ---- | -------- | ----------- | ------------------------- |
| 389  | TCP/UDP  | LDAP        | Identity services         |
| 636  | TCP      | LDAPS       | Secure LDAP               |
| 88   | TCP/UDP  | Kerberos    | Enterprise authentication |
| 1812 | UDP      | RADIUS      | VPN / AAA                 |
| 500  | UDP      | IPSec       | VPN                       |
| 4500 | UDP      | IPSec NAT-T | VPN                       |

---

## 📦 **CI/CD & DevOps Tools**

| Port | Tool              | Usage             |
| ---- | ----------------- | ----------------- |
| 8080 | Jenkins           | CI server UI      |
| 8443 | Jenkins / K8s API | Secure APIs       |
| 9000 | SonarQube         | Code quality      |
| 3000 | Grafana           | Dashboards        |
| 9090 | Prometheus        | Metrics           |
| 5601 | Kibana            | Log visualization |
| 9418 | Git               | Git protocol      |
| 22   | GitHub / GitLab   | Git over SSH      |

---

## 🐳 **Containers & Kubernetes**

| Port        | Component             | Purpose          |
| ----------- | --------------------- | ---------------- |
| 2375        | Docker                | ❌ Unsecured API  |
| 2376        | Docker                | Secure API (TLS) |
| 6443        | Kubernetes API Server | Cluster control  |
| 10250       | Kubelet               | Node management  |
| 30000–32767 | NodePort              | External access  |
| 443         | Ingress               | HTTPS traffic    |

---

## ☁️ **Cloud & Infrastructure**

| Port  | Service       | Usage           |
| ----- | ------------- | --------------- |
| 3306  | MySQL         | Application DB  |
| 5432  | PostgreSQL    | App & analytics |
| 1433  | MSSQL         | Enterprise DB   |
| 27017 | MongoDB       | NoSQL DB        |
| 6379  | Redis         | Cache/session   |
| 9200  | Elasticsearch | Search & logs   |

---

## 📊 **Monitoring & Logging**

| Port | Tool          | Purpose       |
| ---- | ------------- | ------------- |
| 9100 | Node Exporter | Linux metrics |
| 9093 | Alertmanager  | Alerts        |
| 5044 | Logstash      | Log ingestion |
| 8125 | StatsD        | Metrics       |
| 2003 | Graphite      | Metrics       |

---

## 📨 **Messaging & Queues**

| Port  | Tool     | Usage           |
| ----- | -------- | --------------- |
| 5672  | RabbitMQ | Message broker  |
| 9092  | Kafka    | Event streaming |
| 61616 | ActiveMQ | Messaging       |

---

## 🧠 **DevOps Interview Tips**

✔ **SSH (22)** must always be restricted
✔ **K8s API (6443)** should be private
✔ **Never expose Docker 2375 publicly**
✔ **Use HTTPS (443) everywhere**
✔ **NodePort range** is often blocked in production

---




## 🧱 1️⃣ Basic Client–Server Networking (Foundation)

![Image](https://substackcdn.com/image/fetch/%24s_%21F636%21%2Cf_auto%2Cq_auto%3Agood%2Cfl_progressive%3Asteep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fa29b682c-cff6-4ed3-a085-4347eb020b06_1906x1150.png)

![Image](https://upload.wikimedia.org/wikipedia/commons/thumb/c/c9/Client-server-model.svg/1200px-Client-server-model.svg.png)

![Image](https://upload.wikimedia.org/wikipedia/commons/c/c9/Client-server-model.svg)

### 📌 Architecture

```
[ Client ]  --->  [ Server ]
(Browser)        (App / API)
```

### 🔹 Key Concepts

* Client sends request (HTTP/HTTPS)
* Server processes and responds
* IP address + Port (e.g., 80, 443)
* DNS resolves domain → IP

### 🧠 DevOps Use

* Web apps
* APIs
* Health checks
* Curl / Postman testing

---

## 🌐 2️⃣ Three-Tier Architecture (Classic Web App)

![Image](https://vfunction.com/wp-content/uploads/2024/05/blog-3-tier-application.webp)

![Image](https://ipcisco.com/wp-content/uploads/2020/04/3-tier-architecture.jpg)

### 📌 Architecture

```
[ Client ]
    ↓
[ Web Tier ]   →  Nginx / Apache
    ↓
[ App Tier ]   →  Backend (Java, .NET, Node)
    ↓
[ DB Tier ]    →  MySQL / PostgreSQL
```

### 🔹 Key Concepts

* Separation of concerns
* Internal vs external traffic
* Firewall rules between tiers
* Ports: 80 → 8080 → 3306

### 🧠 DevOps Use

* CI/CD deployments
* Blue-Green releases
* Security hardening
* Monitoring per tier

---

## ☁️ 3️⃣ Cloud VPC Networking (AWS / Azure / GCP)

![Image](https://docs.aws.amazon.com/images/prescriptive-guidance/latest/integrate-third-party-services/images/p2_vpc-peering.png)

![Image](https://learn.microsoft.com/en-us/azure/well-architected/service-guides/_images/v-net.png)

![Image](https://docs.aws.amazon.com/images/vpc/latest/userguide/images/how-it-works.png)

### 📌 Architecture

```
VPC / VNet (10.0.0.0/16)
│
├── Public Subnet (10.0.1.0/24)
│    └── Load Balancer / Bastion
│
├── Private Subnet (10.0.2.0/24)
│    └── App Servers
│
└── DB Subnet (10.0.3.0/24)
     └── Database
```

### 🔹 Key Concepts

* CIDR blocks
* Public vs Private subnets
* Route tables
* Internet Gateway / NAT Gateway

### 🧠 DevOps Use

* Terraform IaC
* Secure architectures
* Zero-trust networking
* Production environments

---

## 🐳 4️⃣ Docker Networking Architecture

![Image](https://media.geeksforgeeks.org/wp-content/uploads/20230426184651/microsoft-azure-load-balancing.webp)

![Image](https://blogs.cisco.com/gcs/ciscoblogs/1/2022/08/docker-bridge-1-768x478.jpeg)

![Image](https://media2.dev.to/dynamic/image/width%3D1000%2Cheight%3D420%2Cfit%3Dcover%2Cgravity%3Dauto%2Cformat%3Dauto/https%3A%2F%2Fdev-to-uploads.s3.amazonaws.com%2Fuploads%2Farticles%2Fiqcp0sjzh8mgaocznkx9.png)

### 📌 Architecture

```
[ Container A ] ─┐
                 ├─ Docker Bridge (docker0)
[ Container B ] ─┘
        │
     Host Network
```

### 🔹 Network Types

* Bridge (default)
* Host
* Overlay (Swarm)
* None

### 🧠 DevOps Use

* Microservices communication
* Docker Compose
* Port mapping (`-p 8080:80`)
* Local testing environments

---

## ☸️ 5️⃣ Kubernetes Networking (Pods & Services)

![Image](https://opensource.com/sites/default/files/2022-05/1containerandpodnets.jpg)

![Image](https://outshift-headless-cms-s3.s3.us-east-2.amazonaws.com/blog/k8s-ingress/ingress-fanout-1.png)

![Image](https://kubernetes.io/docs/images/kubernetes-cluster-network.svg)

### 📌 Architecture

```
[ Internet ]
     ↓
[ Ingress ]
     ↓
[ Service ]
     ↓
[ Pod A ] [ Pod B ] [ Pod C ]
```

### 🔹 Key Concepts

* Pod IP (flat network)
* Service (ClusterIP / NodePort / LoadBalancer)
* Ingress Controller
* CNI (Calico, Flannel)

### 🧠 DevOps Use

* AKS / EKS / GKE
* Rolling deployments
* Auto-scaling
* Service discovery

---

## 🔐 6️⃣ DevOps CI/CD Networking Flow

![Image](https://learn.microsoft.com/en-us/azure/devops/pipelines/architectures/media/azure-devops-ci-cd-architecture.svg?view=azure-devops)

![Image](https://www.jenkins.io/images/developer/architecture/jenkins-dataflow.png)

![Image](https://www.cyberark.com/wp-content/uploads/2021/11/cicd-pipelines-1.png)

### 📌 Architecture

```
Developer
   ↓
Git Repository
   ↓
CI Server (Jenkins/GitHub Actions)
   ↓
Artifact Repo / Container Registry
   ↓
Kubernetes / Cloud VM
```

### 🔹 Key Concepts

* Webhooks
* Firewall openings
* SSH / HTTPS access
* Private runners

### 🧠 DevOps Use

* Secure pipelines
* Network-restricted agents
* Artifact security
* Enterprise CI/CD

---

## 🎯 Interview-Ready Summary

| Area              | Must Know                 |
| ----------------- | ------------------------- |
| Networking Basics | IP, CIDR, Ports, DNS      |
| Cloud             | VPC/VNet, Subnets, Routes |
| Containers        | Bridge, Overlay           |
| Kubernetes        | Pod, Service, Ingress     |
| DevOps            | CI/CD network flow        |

---

## 🌐 **DevOps Networking Commands to Remember (Interview + Production Ready)**

As a **DevOps / Cloud engineer**, networking commands are used **daily** for debugging CI/CD, containers, Kubernetes, cloud VMs, and production outages.
Below is a **clean, categorized, must-remember command list** (Linux-first, cloud-ready).

---

## 🔹 1. Basic Network Inspection (Linux)

![Image](https://greenwebpage.com/community/wp-content/uploads/2024/11/word-image-12711-2.png)

![Image](https://media.geeksforgeeks.org/wp-content/uploads/20200512153722/To-display-the-IP-kernel-routing-table.png)

![Image](https://media.geeksforgeeks.org/wp-content/uploads/20190322213932/ooure42.jpg)

![Image](https://www.ricmedia.com/images/216.webp)

```bash
ip a            # Show IP addresses
ip link         # Show network interfaces
ip route        # Routing table
hostname        # Hostname
hostname -I     # IP address of host
cat /etc/hosts  # Local DNS mappings
cat /etc/resolv.conf  # DNS servers
```

📌 **Remember**

* `ip` replaces `ifconfig` and `route`
* Preferred in modern Linux & containers

---

## 🔹 2. Connectivity & Reachability Testing

![Image](https://media.geeksforgeeks.org/wp-content/uploads/20231208125710/6.jpg)

![Image](https://media.geeksforgeeks.org/wp-content/uploads/traceroute.png)

![Image](https://media.geeksforgeeks.org/wp-content/uploads/20240526141558/1.png)

![Image](https://og-image.labex.io/labs/linux-how-to-test-server-connectivity-with-curl-in-linux-415082?lang=en)

```bash
ping google.com           # Check reachability
ping -c 5 8.8.8.8         # Limited pings
traceroute google.com     # Network path
mtr google.com            # Ping + traceroute (best tool)
```

📌 **DevOps Use Case**

* CI agent → GitHub unreachable?
* Pod → DB connection failing?

---

## 🔹 3. DNS & Name Resolution

![Image](https://www.cloudns.net/blog/wp-content/uploads/2018/10/1.png)

![Image](https://upload.wikimedia.org/wikipedia/commons/0/0f/DiG_9.18.1_screenshot.png)

![Image](https://media.geeksforgeeks.org/wp-content/uploads/host-1-1.png)

```bash
nslookup google.com
dig google.com
dig +short google.com
host google.com
```

📌 **Remember**

* `dig` is most powerful
* Kubernetes DNS issues = `dig` inside pod

---

## 🔹 4. Port, Service & Socket Debugging

![Image](https://media.geeksforgeeks.org/wp-content/uploads/all_port-1.png)

![Image](https://training.linuxfoundation.org/wp-content/uploads/2018/06/ss_main.jpg)

![Image](https://www.tecmint.com/wp-content/uploads/2018/11/lsof-specify-port-to-find-application.png)

![Image](https://cdn.comparitech.com/wp-content/uploads/2018/09/What-is-tcpdump_.jpg)

```bash
netstat -tulnp        # Listening ports (legacy)
ss -tulnp             # Modern replacement
lsof -i :8080         # Who is using port 8080
```

📌 **Interview Tip**

* **Use `ss`, not `netstat`** (netstat deprecated)

---

## 🔹 5. HTTP / API Testing (Very Important)

![Image](https://blog.openreplay.com/images/making-http-requests-with-curl/images/image1.png)

![Image](https://codeahoy.com/img/curl-request-response-header.png)

![Image](https://upload.wikimedia.org/wikipedia/commons/6/60/Wget_1.13.4.png)

```bash
curl https://example.com
curl -I https://example.com          # Headers only
curl -v https://example.com          # Verbose
curl -X POST -d '{}' https://api.com
wget https://example.com/file.zip
```

📌 **Used in**

* Health checks
* CI pipelines
* API testing
* Kubernetes readiness probes

---

## 🔹 6. Firewall & Security (Linux)

![Image](https://media.licdn.com/dms/image/v2/C5612AQFBM12gJzEdCw/article-cover_image-shrink_600_2000/article-cover_image-shrink_600_2000/0/1576325460345?e=2147483647\&t=CFvRWzP3RXdLUI3mvZUO2SuNZnDKc8q0bNyPJMQGGaI\&v=beta)

![Image](https://linuxhandbook.com/content/images/2022/12/check-status-of-UFW-logging-in-linux.png)

![Image](https://www.linuxteck.com/wp-content/uploads/2020/04/pre-defined_zones-2.jpg)

```bash
iptables -L -n        # List rules
ufw status            # Ubuntu firewall
ufw allow 8080
firewall-cmd --list-all
```

📌 **Cloud Note**

* Cloud SG/NACL first, OS firewall second

---

## 🔹 7. Packet Capture & Traffic Analysis (Advanced)

```bash
tcpdump -i eth0
tcpdump -i eth0 port 80
tcpdump -i eth0 -n
```

📌 **Production Debugging**

* TLS issues
* Intermittent packet loss
* Kubernetes CNI debugging

---

## 🔹 8. Kubernetes Networking (Critical)

![Image](https://madhuakula.com/content/attacking-and-auditing-docker-containers-and-kubernetes-clusters/kubernetes-101/images/kubectl-combined.png)

![Image](https://www.warp.dev/static/image/r/w%3D3840%2Cq%3D80%2Cformat%3Dauto/g_A_Iu2_M_da1cc75bfa.png)

![Image](https://miro.medium.com/1%2A_rX38dzgl5h9cNcg9Hu_PA.gif)

```bash
kubectl get nodes -o wide
kubectl get pods -o wide
kubectl get svc
kubectl describe svc my-service
kubectl port-forward pod/mypod 8080:80
```

📌 **Debug Flow**
Pod → Service → Endpoint → Ingress → LoadBalancer

---

## 🔹 9. Docker & Container Networking

![Image](https://media.geeksforgeeks.org/wp-content/uploads/20201029185850/Screenshotfrom20201029185836.png)

![Image](https://media.geeksforgeeks.org/wp-content/uploads/20240310181940/Screenshot-%28658%29.webp)

![Image](https://linuxhandbook.com/content/images/2025/04/docker-port-mapping.png)

```bash
docker network ls
docker network inspect bridge
docker inspect container_name
docker port container_name
```

📌 **Remember**

* Containers have **internal IPs**
* Use **port mapping or service mesh**

---

## 🔹 10. Cloud VM & Load Balancer Checks

```bash
curl http://localhost
curl http://<private-ip>
curl http://<load-balancer-dns>
```

📌 **Used in AWS / Azure / GCP**

* ALB / ELB / Azure LB
* VM health probes

---

## 🔹 11. Quick Troubleshooting Flow (Must Remember)

```text
DNS issue?        → dig / nslookup
Port open?        → ss / lsof
Service running? → systemctl status
HTTP issue?       → curl -v
Packet issue?     → tcpdump
K8s issue?        → kubectl describe
```

---

## 🔹 12. Top 15 Commands You MUST Memorize

```bash
ip a
ip route
ping
traceroute
mtr
dig
nslookup
ss -tulnp
lsof -i
curl -v
wget
tcpdump
kubectl get svc
docker network ls
netstat -tulnp
```

---



## 🌐 **Networking for DevOps — Complete Practical Guide**

![Image](https://media.licdn.com/dms/image/v2/D5612AQFatlf0id1KTA/article-cover_image-shrink_720_1280/article-cover_image-shrink_720_1280/0/1720895006720?e=2147483647\&t=PVZMEzHFy9KQNbsLMqKtpAaAXnK7uGx9KE1NuaDr0uU\&v=beta)

![Image](https://docs.oracle.com/cd/E26505_01/html/E27061/figures/ipov.fig88.png)

![Image](https://i.sstatic.net/6qeu7.jpg)

![Image](https://opensource.com/sites/default/files/2022-05/1containerandpodnets.jpg)

![Image](https://docs.aws.amazon.com/images/vpc/latest/userguide/images/how-it-works.png)

Networking is a **core DevOps skill** because every CI/CD pipeline, container, VM, and cloud service communicates over a network. Below is a **clear, interview-ready + hands-on oriented guide**, suitable for training, labs, and real projects.

---

## 1️⃣ Networking Basics Every DevOps Engineer Must Know

### 🔹 OSI & TCP/IP Models (Interview Favorite)

| OSI Layer   | TCP/IP         | DevOps Relevance               |
| ----------- | -------------- | ------------------------------ |
| Application | Application    | HTTP, HTTPS, DNS, APIs         |
| Transport   | Transport      | TCP vs UDP, Ports              |
| Network     | Internet       | IP, Routing                    |
| Data Link   | Network Access | MAC, ARP                       |
| Physical    | Network Access | NIC, cables (cloud abstracted) |

✔ **Why it matters:** Debugging connectivity, TLS, latency, and service failures.

---

## 2️⃣ IP Addressing & Subnetting (Very Important)

### 🔹 IPv4 Basics

* Format: `192.168.1.10`
* Private ranges:

  * `10.0.0.0/8`
  * `172.16.0.0/12`
  * `192.168.0.0/16`

### 🔹 CIDR (Classless Inter-Domain Routing)

* `/24` → 256 IPs
* `/16` → 65,536 IPs

🧠 **DevOps Use Case**

* Designing VPCs
* Kubernetes Pod IP ranges
* Avoiding IP conflicts in hybrid cloud

---

## 3️⃣ Ports & Protocols (Daily Usage)

| Protocol   | Port | Used In         |
| ---------- | ---- | --------------- |
| HTTP       | 80   | Web apps        |
| HTTPS      | 443  | Secure APIs     |
| SSH        | 22   | Servers, Git    |
| DNS        | 53   | Name resolution |
| SMTP       | 25   | Alerts, emails  |
| MySQL      | 3306 | Databases       |
| PostgreSQL | 5432 | Databases       |

🧪 **Lab**

```bash
netstat -tulnp
ss -lntup
```

---

## 4️⃣ DNS (Critical for Microservices)

### 🔹 What DNS Does

* Converts domain → IP
* Example: `api.myapp.com → 10.0.1.15`

### 🔹 DevOps Scenarios

* Blue-Green deployments
* Service discovery
* Failover routing

🧪 **Commands**

```bash
nslookup google.com
dig myservice.cluster.local
```

---

## 5️⃣ Load Balancers & Reverse Proxies

![Image](https://journaldev.nyc3.cdn.digitaloceanspaces.com/2019/03/nginx-reverse-proxy.png)

![Image](https://techdocs.broadcom.com/content/broadcom/techdocs/us/en/vmware-cis/nsx/nsxt-dc/3-2/_jcr_content/assetversioncopies/65fb39a6-5a37-4d12-82c2-ca1db9cf89ee.original.png)

![Image](https://media.geeksforgeeks.org/wp-content/uploads/20240506105314/Kubernetes-Ingress-Architecture-%281%29.webp)

### 🔹 Types

* **L4 Load Balancer** → TCP/UDP (Fast)
* **L7 Load Balancer** → HTTP/HTTPS (Smart routing)

### 🔹 Popular Tools

* **NGINX**
* **HAProxy**
* Cloud LB (AWS ALB/NLB, Azure LB)

🧪 **NGINX Example**

```nginx
location / {
  proxy_pass http://backend;
}
```

---

## 6️⃣ Firewalls, Security Groups & Network ACLs

### 🔹 DevOps Security Layers

| Layer          | Example         |
| -------------- | --------------- |
| Host Firewall  | iptables        |
| Cloud Firewall | Security Groups |
| Network ACL    | Subnet level    |
| App Layer      | WAF             |

🧪 **Linux Firewall**

```bash
iptables -L
ufw status
```

---

## 7️⃣ Container Networking (Docker)

![Image](https://miro.medium.com/v2/resize%3Afit%3A1060/0%2AcMUND9w1bO1o5sPe.png)

![Image](https://media.geeksforgeeks.org/wp-content/uploads/20240215171346/image-189.webp)

![Image](https://docker-k8s-lab.readthedocs.io/en/latest/_images/docker-overlay.png)

### 🔹 Docker Network Types

| Type    | Use Case         |
| ------- | ---------------- |
| bridge  | Single host      |
| host    | High performance |
| overlay | Multi-host       |
| macvlan | Legacy apps      |

🧪 **Commands**

```bash
docker network ls
docker inspect bridge
```

---

## 8️⃣ Kubernetes Networking (Must-Know)

![Image](https://opensource.com/sites/default/files/2022-05/1containerandpodnets.jpg)

![Image](https://assets.bytebytego.com/diagrams/0005-4-k8s-service-types.png)

![Image](https://kubernetes-sigs.github.io/aws-load-balancer-controller/v1.1/imgs/controller-design.png)

### 🔹 Core Concepts

* Every **Pod gets its own IP**
* Flat network (no NAT between pods)
* CNI plugins handle routing

### 🔹 Service Types

| Type         | Purpose      |
| ------------ | ------------ |
| ClusterIP    | Internal     |
| NodePort     | Dev/Test     |
| LoadBalancer | Production   |
| Ingress      | HTTP routing |

🔧 Tools:

* **Kubernetes**
* Calico, Flannel, Cilium

---

## 9️⃣ Cloud Networking (AWS / Azure / GCP)

### 🔹 Core Components

* VPC / VNet
* Subnets (Public / Private)
* Internet Gateway
* NAT Gateway
* Route Tables

🧠 **Real-World DevOps Design**

```
Internet → ALB → App Subnet → DB Subnet
```

🔗 Used heavily in CI/CD deployments & microservices.

---

## 🔟 Networking for CI/CD Pipelines

### 🔹 Jenkins / GitHub Actions Needs:

* Internet access for repos
* Firewall rules for agents
* Secure secrets transfer
* Webhook connectivity

🧪 **Troubleshooting**

```bash
curl -v https://repo.example.com
telnet host port
traceroute google.com
```

---

## 1️⃣1️⃣ Monitoring & Troubleshooting Tools

| Tool       | Purpose        |
| ---------- | -------------- |
| ping       | Connectivity   |
| traceroute | Path analysis  |
| tcpdump    | Packet capture |
| wireshark  | Deep analysis  |
| curl       | API testing    |
| nc         | Port testing   |

---

## 1️⃣2️⃣ Common DevOps Networking Issues (Interview)

✔ Pod not reachable → CNI issue
✔ Service not accessible → Wrong Service Type
✔ CI job fails → Firewall / Proxy
✔ App slow → DNS / LB latency
✔ HTTPS error → TLS / cert misconfig

---

## 📌 DevOps Interview One-Liners

* “Every Pod has its own IP in Kubernetes.”
* “Security Groups are stateful, NACLs are stateless.”
* “Ingress works at Layer 7.”
* “Docker bridge uses NAT.”

---

