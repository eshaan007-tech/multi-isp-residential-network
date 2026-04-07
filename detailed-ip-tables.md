# 📊 Detailed IP Addressing Tables

## 🌐 WAN Configuration

### ACT Junction 1 (Network: 10.1.0.0/24, Gateway: 10.1.0.1)

| House | WAN IP Address | Gateway |
|-------|----------------|---------|
| House 1 | 10.1.0.10 | 10.1.0.1 |
| House 2 | 10.1.0.11 | 10.1.0.1 |
| House 3 | 10.1.0.12 | 10.1.0.1 |

### Airtel Junction (Network: 10.2.0.0/24, Gateway: 10.2.0.1)

| House | WAN IP Address | Gateway |
|-------|----------------|---------|
| House 4 | 10.2.0.4 | 10.2.0.1 |
| House 6 (Router A) | 10.2.0.6 | 10.2.0.1 |

### ACT Junction 2 (Network: 10.3.0.0/24, Gateway: 10.3.0.1)

| House | WAN IP Address | Gateway |
|-------|----------------|---------|
| House 6 (Router B) | 10.3.0.6 | 10.3.0.1 |
| House 7 | 10.3.0.7 | 10.3.0.1 |
| House 8 | 10.3.0.8 | 10.3.0.1 |
| House 9 | 10.3.0.9 | 10.3.0.1 |
| House 10 | 10.3.0.10 | 10.3.0.1 |

---

## 🏠 LAN Configuration (per house)

Each house has a dedicated private `/24` subnet. The router acts as default gateway (`.1`) and provides DHCP in the range `.100 – .149`.

| House | LAN Network | Router LAN IP | DHCP Range |
|-------|-------------|---------------|-------------|
| House 1 | 192.168.10.0/24 | 192.168.10.1 | 192.168.10.100 – 149 |
| House 2 | 192.168.20.0/24 | 192.168.20.1 | 192.168.20.100 – 149 |
| House 3 | 192.168.30.0/24 | 192.168.30.1 | 192.168.30.100 – 149 |
| House 4 | 192.168.100.0/24 | 192.168.100.1 | 192.168.100.100 – 149 |
| House 6 (Airtel) | 192.168.110.0/24 | 192.168.110.1 | 192.168.110.100 – 149 |
| House 6 (ACT) | 192.168.111.0/24 | 192.168.111.1 | 192.168.111.100 – 149 |
| House 7 | 192.168.40.0/24 | 192.168.40.1 | 192.168.40.100 – 149 |
| House 8 | 192.168.50.0/24 | 192.168.50.1 | 192.168.50.100 – 149 |
| House 9 | 192.168.60.0/24 | 192.168.60.1 | 192.168.60.100 – 149 |
| House 10 | 192.168.70.0/24 | 192.168.70.1 | 192.168.70.100 – 149 |

---

## 🔁 Dual ISP – House 6 Details

House 6 has **two independent routers** for redundancy:

| Provider | WAN IP | WAN Gateway | LAN Network | LAN Gateway | DHCP Range |
|----------|--------|-------------|-------------|-------------|-------------|
| Airtel | 10.2.0.6 | 10.2.0.1 | 192.168.110.0/24 | 192.168.110.1 | 192.168.110.100–149 |
| ACT | 10.3.0.6 | 10.3.0.1 | 192.168.111.0/24 | 192.168.111.1 | 192.168.111.100–149 |

Both routers operate independently, simulating residential dual-provider connectivity.

---

## 📝 Subnet Mask Reference

All LAN subnets use **255.255.255.0** (/24).  
All WAN subnets use **255.255.255.0** (/24).

---

*For any questions or clarifications, refer to the main README or open an issue.*
