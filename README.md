# 🚀 Distributed Authentication Platform

![Kubernetes](https://img.shields.io/badge/Kubernetes-GKE-blue)
![Cloud](https://img.shields.io/badge/Cloud-GCP%20%7C%20AWS-orange)
![Architecture](https://img.shields.io/badge/Architecture-Multi--Region-green)
![Availability](https://img.shields.io/badge/Availability-99.9%25-success)
![Scale](https://img.shields.io/badge/Scale-7K%2B%20TPS-critical)

Enterprise-grade authentication system designed for high-scale platforms to handle **7K+ TPS** with **multi-region resiliency** and **zero-downtime architecture**.

---

## 🧩 The Problem

Large-scale platforms (fintech, high-traffic systems) rely on legacy authentication services that break under peak load and regional outages.  
Teams repeatedly face incidents during traffic spikes and migrations due to tight coupling and lack of resiliency.  
This leads to downtime, poor user experience, and high operational risk.

---

## 💡 The Solution

Built a **cloud-native authentication platform** on Kubernetes with:
- Multi-region active/passive architecture  
- High-availability data replication  
- Intelligent failover routing  
- Degraded login mode for outage resilience  

---

## 🏗️ Architecture

```

```
            ┌────────────────────────────┐
            │        Global Users        │
            └────────────┬───────────────┘
                         │
                ┌────────▼────────┐
                │  Load Balancer  │
                └────────┬────────┘
                         │
    ┌────────────────────┴────────────────────┐
    │                                         │
```

┌───────▼────────┐                      ┌─────────▼───────┐
│ Region A (Active)│                    │ Region B (Passive)│
│  GKE Cluster     │                    │  GKE Cluster      │
│  Auth Services   │                    │  Standby Services │
└───────┬─────────┘                      └─────────┬───────┘
│                                         │
└───────────┬─────────────────────────────┘
│
┌───────────▼───────────┐
│  Data Replication     │
│ (HA Sync / DB Layer)  │
└───────────────────────┘

````

---

## 🎬 Demo

**What happens during failure:**
- Traffic automatically reroutes to healthy region 
- System activates degraded login mode  
- Observability dashboards reflect system state in real-time  

---

## 🧪 Example

**Input:**
User login request during peak traffic or partial outage

**Output:**
Successful authentication with automatic failover or degraded mode handling

---

## ⚙️ How It Works

The platform runs on **multi-region Kubernetes clusters** with traffic routing and failover controls.
A replication layer ensures data consistency across environments.
During failures, traffic is rerouted and degraded-mode logic ensures availability.
Observability systems provide real-time system health insights.

---

## ⚖️ Tradeoffs and Decisions

**Why active/passive over active/active:**
Reduced complexity and minimized data consistency risks during initial rollout.

**What I'd do differently:**
Move to **active/active multi-region** with global load balancing.

---

## 🧠 What I Learned

* Designing for failure first improves reliability dramatically
* Cross-team dependencies are harder than technical problems
* Degraded modes are essential for real-world systems

---

## 🚀 Next Steps

* Active/active architecture
* Intelligent traffic routing
* Anomaly detection for proactive failover

---

## 🛠️ Built With

* Kubernetes (GKE)
* Terraform
* Cloud IAM
* Observability tools

---

## 👨‍💻 Author

**Gaurav Kumar**
🔗 [https://www.linkedin.com/in/gauravkumar2](https://www.linkedin.com/in/gauravkumar2)

