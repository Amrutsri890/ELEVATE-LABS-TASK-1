# ELEVATE-LABS-TASK-1 -> Network Security Scanner - Local Port Discovery
Learn to discover open ports on devices in your local network to understand  network exposure.

## 🔍 Project Overview

This cybersecurity project focuses on **local network reconnaissance** using industry-standard tools to discover open ports and running services. The implementation follows ethical hacking principles and is designed for educational and defensive security purposes.

### Key Objectives
- Discover live hosts within target subnets
- Enumerate open TCP services and ports
- Assess immediate network attack surface
- Document security exposures and risks
- Build practical network discovery skills

## 🛠️ Tools & Technologies

- **Primary Tool**: Nmap (Network Mapper)
- **Scanning Method**: TCP SYN Scan (`-sS`)
- **Target Analysis**: Top 20 TCP ports database
- **Documentation**: Security assessment reporting

## 🎯 Technical Implementation

### Scanning Command
```bash
nmap -sS -Pn --top-ports 20 -T4 <target_subnet> -oN output_file.txt
```

### Command Parameters Explained
- `-sS`: TCP SYN scan (stealth scanning)
- `-Pn`: Skip host discovery, treat all hosts as online
- `--top-ports 20`: Scan the 20 most common ports
- `-T4`: Aggressive timing for faster scans
- `-oN`: Normal output format to file

### Target Networks
- **Primary Subnet**: `192.168.12.0/24`
- **Test Environment**: `10.0.72.0/21`
- **Scope**: Local network infrastructure

## 📊 Scan Results Summary

### Discovered Services

| Host | Open Ports | Services | Risk Level |
|------|------------|----------|------------|
| 10.0.72.1 | 22, 23, 80 | SSH, Telnet, HTTP | High (Telnet) |
| 10.0.72.8 | All Filtered | Firewall Protected | Low |
| 10.0.76.169 | 135, 139, 445 | Windows Services | Medium |

### Key Findings
- **46 hosts discovered** in the target range
- **Multiple service exposures** identified
- **Critical Telnet service** (insecure protocol)
- **Windows file sharing** services exposed

## 🔒 Security Assessment

### Identified Risks
1. **Telnet Service (Port 23)**: Unencrypted communication protocol
2. **HTTP Service (Port 80)**: Potential web application vulnerabilities  
3. **SMB Services (Ports 139/445)**: File sharing attack vectors
4. **SSH Service (Port 22)**: Brute force attack target

### Recommended Mitigations
- Replace Telnet with secure SSH connections
- Implement HTTPS for web services
- Restrict SMB access with proper authentication
- Configure strong SSH key-based authentication
- Deploy network segmentation and firewalls
- Regular security patching and updates

## 🎓 Educational Value

This project demonstrates:
- **Network Reconnaissance Techniques**
- **Port State Classification** (Open/Closed/Filtered)
- **Service Enumeration Methods**
- **Security Risk Assessment**
- **Ethical Hacking Practices**

### Learning Outcomes
- Understanding TCP/IP networking fundamentals
- Practical experience with Nmap scanning
- Network security assessment methodology
- Documentation and reporting skills
- Cybersecurity threat identification

## ⚖️ Ethical Guidelines

This project follows **responsible disclosure** and ethical hacking principles:
- Scanning performed only on authorized networks
- No exploitation of discovered vulnerabilities
- Educational and defensive security purposes
- Proper documentation and risk assessment
- Adherence to legal and institutional policies

## 📁 Project Structure

```
├── README.md
├── scan_results/
│   ├── nmap_quick_scan.txt
│   └── detailed_analysis.pdf
├── documentation/
│   └── security_assessment_report.pdf
└── screenshots/
    ├── nmap_output_1.png
    ├── nmap_output_2.png
    └── nmap_output_3.png
```

## 🚀 Getting Started

### Prerequisites
- Nmap installed on scanning system
- Authorization for target network scanning
- Understanding of network security principles

### Installation
```bash
# Ubuntu/Debian
sudo apt-get install nmap

# CentOS/RHEL
sudo yum install nmap

# Windows
# Download from https://nmap.org/download.html
```

### Basic Usage
```bash
# Quick subnet scan
nmap -sS -Pn --top-ports 20 -T4 192.168.1.0/24

# Detailed service detection
nmap -sS -sV -Pn 192.168.1.0/24

# Output to file
nmap -sS -Pn --top-ports 20 192.168.1.0/24 -oN scan_results.txt
```

## 📚 Additional Resources

### Network Security Fundamentals
- TCP/IP Protocol Suite
- Port and Service Concepts  
- Firewall Configuration
- Intrusion Detection Systems

### Advanced Nmap Techniques
- Service Version Detection (`-sV`)
- OS Fingerprinting (`-O`)
- Script Engine (`--script`)
- Timing and Performance Optimization

## 👤 Author

**S. Sai Amrutha**  
*Cybersecurity Student & Security Researcher*  
📧 240160226211.sunkavalli@gdgu.org

### Academic Background
- BTech Computer Science Engineering (Cybersecurity)
- GD Goenka University
- Network Security Specialization

## 📄 License

This project is intended for **educational purposes** and cybersecurity learning. Please ensure compliance with local laws and organizational policies before conducting any network scanning activities.

---

**⚠️ Disclaimer**: This tool is designed for authorized network assessment only. Users are responsible for ensuring proper authorization before scanning any networks. Unauthorized network scanning may violate local laws and institutional policies.
