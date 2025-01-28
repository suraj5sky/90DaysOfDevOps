# 🛠️ Networking Challenge for DevOps:

**This guide dives into essential networking concepts, important protocols and ports, and hands-on AWS EC2 setup for a robust understanding of networking in DevOps.**

---

## 🌐 Tasks Overview

### 1. OSI & TCP/IP Models (with Examples)
#### **OSI Model: A 7-Layer Framework**
The OSI model explains how data travels across a network in seven logical layers:
- **Layer 1: Physical**  
  *Hardware connections and transmission media.*  
  **Examples**: Ethernet cables, Network Interface Cards (NICs).
- **Layer 2: Data Link**  
  *Responsible for MAC addressing and error detection.*  
  **Examples**: Ethernet, ARP, switches.
- **Layer 3: Network**  
  *Manages IP addressing and packet routing.*  
  **Examples**: IP, OSPF, BGP.
- **Layer 4: Transport**  
  *Ensures data delivery (TCP for reliability, UDP for speed).*  
  **Examples**: TCP (web browsing), UDP (video streaming).
- **Layer 5: Session**  
  *Manages sessions and connections between devices.*  
  **Examples**: RPC, NetBIOS.
- **Layer 6: Presentation**  
  *Data translation, compression, and encryption.*  
  **Examples**: SSL/TLS, ASCII, JPEG.
- **Layer 7: Application**  
  *Provides user-facing services.*  
  **Examples**: HTTP (web browsing), SMTP (email), FTP (file transfers).

#### **TCP/IP Model: The Practical Alternative**
The TCP/IP model simplifies networking into four key layers:
| **Layer**       | **Examples**                           | **Equivalent OSI Layers**       |
|------------------|----------------------------------------|----------------------------------|
| **Link**        | Ethernet, PPP                          | Physical, Data Link             |
| **Internet**    | IP (IPv4/IPv6), ICMP                   | Network                         |
| **Transport**   | TCP, UDP                               | Transport                       |
| **Application** | HTTP, DNS, SSH                         | Session, Presentation, Application |

---

### 2. 🔑 Important Protocols and Ports for DevOps
#### **Essential Networking Protocols**
| **Protocol**  | **Port Number** | **Purpose**                  | **DevOps Use Case**             |
|---------------|-----------------|------------------------------|----------------------------------|
| **HTTP**      | 80              | Unsecured web traffic        | Web server access               |
| **HTTPS**     | 443             | Secure web traffic           | Secure communications           |
| **SSH**       | 22              | Remote access                | Server management               |
| **DNS**       | 53              | Domain name resolution       | Kubernetes service discovery    |
| **FTP**       | 20/21           | File transfers               | Uploading files to servers      |
| **MySQL**     | 3306            | Database communication       | Database management in apps     |
| **K8s API**   | 6443            | Kubernetes API communication | Orchestrating containerized apps|


---

### 3. 🚀 AWS EC2 Instance and Security Groups
#### **Steps to Launch an EC2 Instance**
1. **Log in** to the AWS Console and navigate to the EC2 dashboard.
2. **Launch an Instance**:
   - Choose an **AMI**: Use Ubuntu or Amazon Linux.
   - Select an **Instance Type**: Start with `t2.micro` (free tier eligible).
3. **Configure Security Groups**:
   - Allow **SSH (port 22)** for remote management.
   - Allow **HTTP (port 80)** for web server access.
4. **Launch and Connect**:
   - Download the `.pem` key file for authentication.
   - Connect to the instance using SSH:
     ```bash
     ssh -i <key>.pem ubuntu@<EC2-Public-IP>
     ```

#### **Security Groups Best Practices**
- Use **least privilege**: Open only the ports necessary for your application.
- Restrict **inbound traffic** to specific IP ranges.
- Monitor and review rules regularly for compliance.


DevOps journey! 🚀
