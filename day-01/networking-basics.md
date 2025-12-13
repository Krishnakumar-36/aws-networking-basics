# Day 01 – Networking Basics

## 1. Local Network Commands

### ipconfig
- Shows IP address, subnet mask, default gateway
- Helps identify network configuration issues

### ping google.com
- Tests connectivity to an external server
- Uses ICMP protocol
- Confirms internet access

### tracert google.com
- Shows the path packets take to reach destination
- Helps identify network delays or failures

---

## 2. What happens behind the scenes
1. DNS resolves google.com to an IP address
2. ICMP echo request is sent
3. Routers forward packets hop-by-hop
4. Destination replies with echo response

---

## 3. Relation to AWS
- Local IP → EC2 private IP
- Gateway → Internet Gateway (IGW)
- Firewall → Security Group / NACL
- Routing → Route Tables
