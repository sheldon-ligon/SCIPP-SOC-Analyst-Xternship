# Week 1 — Lab Environment Preparation

## Objective

Deploy and validate an isolated vulnerability assessment lab consisting of Greenbone OpenVAS, Metasploitable2, and an analyst workstation. Configure static IP addressing, verify network communication, synchronize the OpenVAS Community Feeds, and confirm that the scanner is ready to assess the target system.

> **Environment Note:** Lubuntu was used as the original analyst workstation during Week 1. It was later replaced with Ubuntu Linux at `192.168.5.10` as the lab environment evolved. The Week 1 screenshots therefore reflect the original Lubuntu workstation.

---

## Lab Environment

| System | IP Address | Purpose |
|---|---|---|
| Greenbone OpenVAS | `192.168.5.5` | Vulnerability scanner |
| Metasploitable2 | `192.168.5.3` | Intentionally vulnerable assessment target |
| Lubuntu Desktop | Historical Week 1 workstation | Lab administration and OpenVAS web access |

**Virtualization Platform:** VMware Workstation  
**Network:** VMware Host-Only  
**Lab Subnet:** `192.168.5.0/24`  
**Gateway:** `192.168.5.1`

---

## Metasploitable2

###Configuration

**Hostname:** Metasploitable2  
**Static IP:** `192.168.5.3`  
**Network Type:** VMware Host-Only

### Commands Used

```bash
ip addr show eth0
ip route
ping -c 4 192.168.5.1
arp -a
```
---

### Validation & Evidence

#### Network Configuration

The Metasploitable2 network configuration was validated using `ip addr` and `ip route`. The `eth0` interface was confirmed operational with the static IPv4 address `192.168.5.3/24`, and the system contained a route for the `192.168.5.0/24` lab network.

![Metasploitable2 Network Configuration](Screenshots/W1-01-Metasploitable-Network-Configuration.png)

*Figure 1 — Metasploitable2 `eth0` interface and routing configuration confirming the assigned lab address.*

#### Network Connectivity

Connectivity to the lab gateway at `192.168.5.1` was tested using ICMP. All four packets were successfully returned with 0% packet loss, confirming communication across the VMware Host-Only network.

![Metasploitable2 Ping Validation](Screenshots/W1-02-Metasploitable-Ping-Host-Validation.png)

*Figure 2 — Successful ICMP connectivity test from Metasploitable2 to the lab gateway.*

#### ARP Validation

The ARP table was reviewed to verify local network neighbor discovery. Metasploitable2 successfully resolved `192.168.5.1` to a MAC address through the `eth0` interface, confirming Layer 2 communication with the VMware Host-Only gateway.

![Metasploitable2 ARP Table Validation](Screenshots/W1-03-Metasploitable-ARP-Table-Validation.png)

*Figure 3 — ARP table showing successful resolution of the lab gateway on the local network.*

---

## VMware Host-Only Network

### Network Configuration

The lab environment was configured using a VMware Host-Only network to provide an isolated network for communication between the vulnerability scanner, analyst workstation, and vulnerable target.

The `VMnet1` virtual network was configured with the `192.168.5.0/24` subnet. VMware DHCP was disabled so that systems within the lab could be assigned static IP addresses.

This configuration allowed the lab systems to communicate with each other while keeping the intentionally vulnerable Metasploitable2 target isolated from the external network.

### Validation & Evidence

![VMware Host-Only Network Configuration](Screenshots/W1-04-VMware-Network-Settings.png)

*Figure 4 — VMware Virtual Network Editor showing VMnet1 configured as a Host-Only network using the `192.168.5.0/24` subnet with VMware DHCP disabled.*


---

## Greenbone OpenVAS

### Initial Deployment

Greenbone OpenVAS Free 25.0.5 was deployed as the vulnerability scanner for the lab environment. The scanner was configured to communicate with the Metasploitable2 target through the isolated VMware Host-Only network.

During the initial deployment, the OpenVAS setup wizard was used to complete the appliance configuration and prepare the scanner for operation.

### Initial Setup

![OpenVAS Initial Setup](Screenshots/W1-05-OpenVAS-Initial-Setup.png)

*Figure 5 — OpenVAS Free 25.0.5 initial setup wizard prior to completing the scanner configuration.*

### Network Configuration

The OpenVAS appliance was assigned the static IPv4 address `192.168.5.5/24` on the `eth0` interface. This placed the scanner on the same `192.168.5.0/24` network as the Metasploitable2 target.

![OpenVAS IP Configuration](Screenshots/W1-06-OpenVAS-IP-Configuration.png)

*Figure 6 — OpenVAS network configuration showing `192.168.5.5/24` assigned to the `eth0` interface.*

### Web Interface Availability

After the initial configuration was completed, Greenbone OS successfully started and reported that the OpenVAS web interface was available at `192.168.5.5`.

![OpenVAS Web Interface Available](Screenshots/W1-07-OpenVAS-Web-Interface-Available.png)

---

## Analyst Workstation

### Original Week 1 Workstation

During Week 1, Lubuntu was used as the analyst workstation for network validation, lab administration, and access to the OpenVAS web interface.

The workstation was configured with the static IPv4 address `192.168.5.6/24` on the `ens33` interface and connected to the isolated `192.168.5.0/24` lab network.

> **Environment Update:** This Lubuntu workstation was later replaced with an Ubuntu Linux workstation using `192.168.5.10`. The following screenshots are retained as historical evidence of the original Week 1 configuration.

### Network Configuration

The workstation's network configuration was validated using `hostname`, `ip addr`, and `ip route`. The `ens33` interface was confirmed operational with the address `192.168.5.6/24` and a route to the `192.168.5.0/24` lab network.

![Lubuntu Network Configuration](Screenshots/W1-08-Lubuntu-Network-Configuration.png)

*Figure 8 — Original Week 1 analyst workstation showing the `ens33` interface configured with `192.168.5.6/24`.*

### Connectivity Validation

Connectivity was tested from the analyst workstation to both primary lab systems:

- OpenVAS scanner — `192.168.5.5`
- Metasploitable2 target — `192.168.5.3`

Both systems successfully responded to all four ICMP requests with 0% packet loss, confirming communication between the analyst workstation, vulnerability scanner, and target system.

![Lubuntu Connectivity Validation](Screenshots/W1-09-Lubuntu-Connectivity-Validation.png)

*Figure 9 — Successful ICMP connectivity from the analyst workstation to both OpenVAS and Metasploitable2.*

### OpenVAS Dashboard Access

After network connectivity was validated, the OpenVAS web interface was accessed from Firefox on the analyst workstation using `192.168.5.5`.

Successful access to the dashboard confirmed that the workstation could communicate with the OpenVAS web service and that the scanner's management interface was operational.

![Lubuntu OpenVAS Dashboard](Screenshots/W1-10-Lubuntu-OpenVAS-Dashboard.png)

*Figure 10 — OpenVAS dashboard successfully accessed from the original Week 1 analyst workstation.*
*Figure 7 — Greenbone OS console confirming that the OpenVAS web interface is available at `192.168.5.5`.*
