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

