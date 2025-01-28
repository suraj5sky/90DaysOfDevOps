# Networking Challenge for DevOps:

This guide covers foundational networking concepts, important protocols and ports.

---

## Tasks Overview

### 1. OSI & TCP/IP Models (with Examples)
- **OSI Model**: A conceptual framework for network communication divided into 7 layers:
  - **Layer 1: Physical**  
    - Examples: Cables (Ethernet), Network Interface Cards (NIC).  
  - **Layer 2: Data Link**  
    - Examples: MAC addresses, Ethernet.  
  - **Layer 3: Network**  
    - Examples: IP, routing protocols (OSPF, BGP).  
  - **Layer 4: Transport**  
    - Examples: TCP, UDP.  
  - **Layer 5: Session**  
    - Examples: Session management (RPC, NetBIOS).  
  - **Layer 6: Presentation**  
    - Examples: Data translation, encryption (SSL/TLS).  
  - **Layer 7: Application**  
    - Examples: HTTP, FTP, SMTP.  

- **TCP/IP Model**: The 4-layer practical networking model:
  - **Link Layer**: Ethernet, PPP.  
  - **Internet Layer**: IP (IPv4/IPv6), ICMP.  
  - **Transport Layer**: TCP, UDP.  
  - **Application Layer**: HTTP, DNS, SSH.  

### Diagram: OSI vs TCP/IP Model
https://github.com/user-attachments/assets/24c7bed7-9ccd-4573-af8a-c3bd2d2c903f

---

### 2. Important Protocols and Ports for DevOps
| Protocol   | Port Number | Purpose                      | DevOps Use Case                  |
|------------|-------------|------------------------------|-----------------------------------|
| **HTTP**   | 80          | Web traffic                 | Accessing web servers            |
| **HTTPS**  | 443         | Secure web traffic          | Secure connections to servers    |
| **SSH**    | 22          | Secure Shell access         | Managing servers remotely        |
| **DNS**    | 53          | Domain resolution           | Service discovery in Kubernetes  |
| **FTP**    | 20/21       | File transfer               | Transferring files to servers    |
| **MySQL**  | 3306        | Database access             | Application databases            |
| **K8s API**| 6443        | Kubernetes API communication| Orchestrating containers         |

### Blog Content
- Write a detailed blog explaining each protocol and its DevOps use case.
- Include examples for configuring services (e.g., `nginx`, `SSH`).

---

### 3. Create an AWS EC2 Instance and Explore Security Groups
#### Steps to Create an EC2 Instance:
1. **Log in to AWS Console**: Navigate to the EC2 service.
2. **Launch an Instance**:
   - Select AMI: Choose Ubuntu or Amazon Linux.
   - Choose Instance Type: `t2.micro` for free tier.
3. **Configure Security Groups**:
   - Allow **SSH (port 22)** for remote management.
   - Allow **HTTP (port 80)** for web traffic.
4. **Launch and Connect**:
   - Use `ssh -i <key>.pem ubuntu@<EC2-Public-IP>` to access the instance.

#### Security Groups Overview:
- **Inbound Rules**:
  - Define traffic allowed into the instance.
- **Outbound Rules**:
  - Define traffic leaving the instance.
- **Best Practices**:
  - Use least privilege by opening only required ports.
  - Restrict access by IP ranges.

---




```
