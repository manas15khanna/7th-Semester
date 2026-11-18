[[IoT Case Studies]]
# IoT Security & Incident Response: Exam Study Guide & Case Study Framework

## Unit 1: Fundamental Concepts & Cyber-Physical Systems (CPS vs. IoT)

### 1. Fundamentals & Definitions

- **Cybersecurity**: The practice of protecting computers, networks, devices, software, data, and connected systems from unauthorized access, attacks, damage, or disruption. In IoT and Cyber-Physical Systems (CPS), cybersecurity extends beyond protecting data to safeguarding physical operations, human safety, and real-world environments.
- **Internet of Things (IoT)**: A broad network of physical objects ("things") embedded with sensors, software, and other technologies that connect to the internet or communication networks to collect, exchange, and process data.
- **Cyber-Physical Systems (CPS)**: Systems that tightly integrate computational engine algorithms, networking, and physical processes. In CPS, embedded computers and networks monitor and control physical processes in real-time feedback loops.

### 2. Comprehensive Comparison: IoT vs. CPS

|   |   |   |
|---|---|---|
|Aspect|Internet of Things (IoT)|Cyber-Physical Systems (CPS)|
|**Definition**|Network of physical devices connected to the internet to collect, exchange, and process data.|Systems that tightly integrate computation, communication, and physical processes for monitoring and control.|
|**Main Focus**|Device connectivity and data-driven service delivery.|Interaction, coordination, and real-time feedback between computing systems and the physical world.|
|**Internet Dependency**|Usually relies heavily on internet and cloud infrastructure.|Can operate with or without the internet; prioritizes local, closed-loop, and real-time networks.|
|**Physical Control**|Primarily monitors environment; may offer basic or indirect control capabilities.|Direct, continuous, and automated control over physical processes via actuators and controllers.|
|**Real-Time Operation**|Real-time execution is often optional or non-critical.|Hard real-time or time-critical operation is essential.|
|**Data Processing**|Emphasizes centralized cloud platforms or edge analytics.|Emphasizes edge, fog, and local processing for rapid control decisions.|
|**Security Concern**|Device, network, data privacy, and cloud security.|**Security plus physical safety, system reliability, timing deadlines, and environmental failure consequences.**|
|**Key Architecture**|Sensors \rightarrow Network Gateway \rightarrow Cloud \rightarrow Application.|Sensors \rightarrow Embedded Computing \rightarrow Control Systems \rightarrow Network \rightarrow Actuators.|
|**Examples**|Smartwatches, smart home appliances, connected tracking devices, smart parking.|Autonomous vehicles, industrial robots, smart power grids, medical life-support systems, aircraft control.|

### 3. Key Security Goals: The CIA Triad in IoT/CPS

Cybersecurity frameworks are evaluated against three fundamental objectives:

```
                  +-----------------------+
                  |  CONFIDENTIALITY      |
                  |  "Who can see data?"  |
                  +-----------+-----------+
                              |
                              |
      +-----------------------+-----------------------+
      |                                               |
+-----+-----------------+                   +---------+-------------+
|    INTEGRITY          |                   |    AVAILABILITY       |
| "Who can change data?"|                   | "Can I access system?"|
+-----------------------+                   +-----------------------+
```

1. **Confidentiality (**_**Who can see?**_**)**: Ensures that sensitive information is accessible only to authorized entities.
    - _Traditional Context_: Protecting personal data or financial records from unauthorized exposure.
    - _IoT/CPS Example_: Preventing unauthorized eavesdropping on wearable healthcare monitors or private smart home video feeds.
2. **Integrity (**_**Who can change?**_**)**: Ensures that data, system configurations, software, and control commands are not altered, forged, or deleted by unauthorized parties.
    - _Traditional Context_: Preventing an unauthorized party from modifying a bank balance.
    - _IoT/CPS Example_: Ensuring an attacker cannot alter temperature readings sent to an Industrial Control System (ICS) or modify actuation commands sent to a Programmable Logic Controller (PLC). **Integrity is often the most critical principle in IoT/CPS.**
3. **Availability (**_**Can I access it?**_**)**: Ensures that systems, networks, devices, and operational data are accessible when required by authorized users or automated systems.
    - _Traditional Context_: Keeping a web server online during business hours.
    - _IoT/CPS Example_: Ensuring a smart grid or connected medical device remains responsive and operational without interruption.

### 4. Why Cybersecurity is Critical in IoT & CPS

1. **Protection of Sensitive Data**: Continuous collection of personal, operational, location, and health metrics requires strict access boundary enforcement.
2. **Prevention of Unauthorized Access**: Exploitation of exposed interfaces or default credentials allows attackers lateral movement into enterprise networks.
3. **Ensuring Physical Safety**: Cyberattacks on CPS directly manipulate physical mechanisms, potentially causing equipment damage, structural fires, or human injury.
4. **Maintaining Critical Service Availability**: Prevents Denial-of-Service (DoS) attacks from paralyzing municipal infrastructure, health networks, or manufacturing plants.

## Threat vs. Vulnerability vs. Risk Framework

### 1. Conceptual Framework & Definitions

- **Threat**: Any potential event, action, or actor capable of exploiting a weakness to cause harm to an asset, system, or process.
- **Vulnerability**: A weakness, security flaw, or hole in hardware, software, network configurations, physical security, or human procedures.
- **Risk**: The probability or likelihood that a specific threat will exploit a specific vulnerability, combined with the potential operational, financial, or safety impact of that event.
- **Security Incident**: An event where a threat successfully exploits a vulnerability, compromising the confidentiality, integrity, availability, or safety of a system.
- **Impact**: The actual damage or loss caused by a security incident (e.g., equipment damage, financial loss, injury, downtime).

### 2. Conceptual Formula & Flow

$$\text{Threat} \xrightarrow{\text{exploits}} \text{Vulnerability} \xrightarrow{\text{creates}} \text{Risk} \xrightarrow{\text{results in}} \text{Security Incident} \xrightarrow{\text{causes}} \text{Impact / Loss}$$

#### Real-World Analogy Framework

|   |   |   |   |
|---|---|---|---|
|Concept|Analogy 1: Home Security|Analogy 2: Smart Factory|Analogy 3: Smart Healthcare|
|**Asset**|House & Valuables|Industrial Machinery & Controllers|Patient Health Data & Monitoring Systems|
|**Threat**|Burglar|Cyber Attacker / Hacker|Malicious Insider / Remote Hacker|
|**Vulnerability**|Unlocked Back Door|Default Passwords & Outdated Firmware|Unencrypted Wireless Transmission|
|**Risk**|Likelihood of break-in and loss of assets|Potential unauthorized access and machine control|Potential data modification or privacy breach|
|**Incident**|Burglar enters through door and steals items|Attacker logs in and changes PLC temperature setpoint|Attacker alters patient heart-rate readings|
|**Impact**|Financial loss, property damage|Production halt, damaged equipment, worker injury|Misdiagnosis, improper drug delivery, loss of life|

### 3. Classification of Security Incidents

#### Incident Categories by Security Impact

```
                  +-----------------------------------+
                  |     SECURITY INCIDENT CATEGORIES  |
                  +-----------------+-----------------+
                                    |
     +---------------+--------------+--------------+---------------+
     |               |              |              |               |
+----+----+    +-----+----+   +-----+----+   +-----+----+    +-----+-----+
|  CONF.  |    | INTEGRITY|   | AVAIL.   |   |   AUTH.  |    |  SAFETY   |
| Privacy |    | Data Mod |   | DoS/DDoS |   | Credential|    | Physical  |
| Breach  |    | Injection|   | Outages  |   | Theft    |    | Harm/Damage|
+---------+    +----------+   +----------+   +----------+    +-----------+
```

- **Confidentiality Incident**: Unauthorized exposure or exfiltration of sensitive data (e.g., medical record leakage).
- **Integrity Incident**: Unauthorized modification of sensor data, system parameters, or control commands (e.g., false sensor readings).
- **Availability Incident**: Disruptions rendering services or devices unusable (e.g., DDoS targeting a smart grid gateway).
- **Authentication Incident**: Compromise of identities or credential theft (e.g., stolen SSH keys or exposed default credentials).
- **Privacy Incident**: Collection or exposure of Personally Identifiable Information (PII) beyond defined consent parameters.
- **Safety Incident**: Cyber-driven manipulation resulting in physical damage, dangerous equipment speeds, or physical risk to humans.

## 4-Stage IoT Architecture & Layer-by-Layer Security

```
+-----------------------------------------------------------------------+
| 4. APPLICATION LAYER                                                  |
| Dashboards, Web Portals, Mobile Apps, Enterprise Systems              |
+-----------------------------------^-----------------------------------+
                                    |
+-----------------------------------v-----------------------------------+
| 3. DATA PROCESSING / EDGE GATEWAY LAYER                               |
| Data Analytics, Cloud Platforms, Stream Processing, Edge Rules        |
+-----------------------------------^-----------------------------------+
                                    |
+-----------------------------------v-----------------------------------+
| 2. NETWORK LAYER                                                      |
| Wi-Fi, Cellular (4G/5G), LoRaWAN, Bluetooth, Routers, Firewalls       |
+-----------------------------------^-----------------------------------+
                                    |
+-----------------------------------v-----------------------------------+
| 1. SENSING / PERCEPTION LAYER                                         |
| Sensors (Temp, Pressure), Actuators (Motors, Valves), Microcontrollers|
+-----------------------------------------------------------------------+
```

### Complete End-to-End Operational Flow

$$\text{Sensors} \rightarrow \text{Wireless Network} \rightarrow \text{Edge Gateway} \rightarrow \text{Cloud Platform} \rightarrow \text{Control Commands} \rightarrow \text{Industrial Actuators / PLCs} \rightarrow \text{Machine}$$

### Layer-by-Layer Threat & Defense Matrix

|   |   |   |   |
|---|---|---|---|
|Architecture Layer|Core Function|Specific Security Threats & Attacks|Layer-Specific Defenses & Controls|
|**1. Sensing / Perception Layer**|Collects physical parameters (temp, pressure, motion) via sensors; executes commands via actuators.|• Physical tampering and hardware destruction.<br>• Device capture, theft, and firmware extraction.<br>• Sensor spoofing & false data injection.<br>• Default or hardcoded credentials.<br>• Resource constraints preventing heavy cryptography.|• Strong device-level authentication.<br>• Secure Boot and signed firmware validation.<br>• Tamper-evident packaging and hardware protection.<br>• Physical security controls in remote deployments.<br>• Plausibility checks on raw sensor measurements.|
|**2. Network Layer**|Transmits data securely across local and wide-area networks; handles routing and addressing.|• Network eavesdropping and packet sniffing.<br>• Man-in-the-Middle (MitM) data modification.<br>• Replay attacks (re-sending legitimate packets).<br>• Distributed Denial of Service (DDoS) / Flooding.<br>• Insecure, unencrypted wireless protocols.|• End-to-End Encryption (TLS/DTLS, IPsec).<br>• Network segmentation and VLAN isolation.<br>• Firewalls and Network Intrusion Detection (NIDS).<br>• Anti-replay mechanisms (timestamps, nonces).<br>• Disabling unnecessary network services/ports.|
|**3. Data Processing / Edge Gateway Layer**|Preprocesses, cleans, filters, aggregates data; routes commands between cloud and edge.|• Edge gateway compromise.<br>• Data manipulation at the point of decryption.<br>• Edge malware infection.<br>• Unauthorized access to edge storage.<br>• Relay of malicious commands to physical networks.|• Message Integrity Checks (HMAC) & Digital Signatures.<br>• Regular patch management and gateway hardening.<br>• Secure boot and hardware root-of-trust (TPM).<br>• Gateway anomaly monitoring and log auditing.<br>• Strict access control policies at the edge boundary.|
|**4. Application Layer**|Interacts with end users; provides dashboards, analytics, and automated decision tools.|• Insecure Web/API endpoints.<br>• Unauthorized application access via credential theft.<br>• Weak user authentication protocols.<br>• SQL injection / Cross-Site Scripting (XSS).<br>• Data privacy violations and unauthorized storage.|• Multi-Factor Authentication (MFA).<br>• Role-Based Access Control (RBAC).<br>• API security (OAuth 2.0, API key management).<br>• Input validation and parameterized queries.<br>• Application layer data encryption and logging.|
|**Actuation Sub-Layer**|Converts control software signals into physical actions (valves, motors, switches).|• Unauthorized command injection.<br>• Parameter manipulation leading to unsafe operational limits.<br>• Emergency stop override attacks.|• Authentication and authorization of control commands.<br>• Hardware-enforced safety limits independent of software.<br>• Emergency physical interlocks and manual overrides.|

### Critical Analysis: Why Encryption Alone is Insufficient

A common flaw in IoT architecture design is relying solely on communication encryption (e.g., TLS). Exam questions frequently test why an encrypted system can still fail:

1. **Compromised Data Source**: Encryption protects the communication channel in transit; it does not validate whether the data source is truthful. If a sensor is physically or logically compromised, it will generate **false data**, which is then cleanly encrypted and sent to the cloud.
2. **Gateway Decryption Points**: End-to-end encryption often terminates at an intermediate edge gateway for data processing or protocol conversion. A compromised gateway can alter data after decryption and re-encrypt the forged payload before sending it to the cloud.
3. **Authentication vs. Integrity vs. Validity**:
    - **Device Authentication**: Confirms _who_ sent the data (e.g., "This message came from Sensor 12").
    - **Data Integrity**: Confirms _whether_ the message was altered in transit (e.g., "The packet was not modified on the wire").
    - **Data Validity**: Confirms _whether_ the content of the data represents reality (e.g., "Is the machine temperature actually 40°C, or is Sensor 12 lying?").

## Essential Incident Response Terminologies & Metrics

### 1. Key Incident Response Concepts

```
+-----------------------------------------------------------------------+
| ATTACK SURFACE (Total exposed entry points: Cameras, Ports, Web Apps) |
|                                                                       |
|   +---------------------------------------------------------------+   |
|   | ATTACK VECTOR (Path used to enter: Default Passwords)         |   |
|   |                                                               |   |
|   |   +-------------------------------------------------------+   |   |
|   |   | THREAT ACTOR (Attacker / Hacker Group)                |   |   |
|   |   +-------------------------------------------------------+   |   |
|   +---------------------------------------------------------------+   |
+-----------------------------------------------------------------------+
```

- **Event**: Any observable occurrence in a system or network (e.g., a firewall blocking a packet, a user logging into a portal).
- **Adverse Event**: An event with negative consequences (e.g., a system crash, network packet flood, unauthorized access attempt).
- **Security Incident**: A violation or imminent threat of violation of computer security policies, acceptable use policies, or standard security practices.
- **Attack Vector**: The specific pathway, method, or technique an attacker uses to gain unauthorized access to a system (e.g., phishing email, default camera password, unpatched software vulnerability).
- **Attack Surface**: The aggregate sum of all potential entry points, vulnerabilities, interfaces, and exposed systems through which an attacker could attempt an intrusion.
- **Threat Actor**: The individual, group, or entity that intentionally executes or facilitates a cyberattack (e.g., nation-state actors, cybercriminals, malicious insiders).
- **Indicator of Compromise (IOC)**: Forensic evidence or artifacts indicating that an attack has occurred or a system has been compromised (e.g., known malicious IP addresses, file hashes, unusual registry edits, unexpected file modifications).
- **Indicator of Attack (IOA)**: Evidence demonstrating proactive, ongoing malicious activity or operational behaviors (e.g., privilege escalation attempts, lateral movement, abnormal internal network scans).
- **TTPs (Tactics, Techniques, and Procedures)**: The pattern of behaviors, technical methods, and operational strategies used by a threat actor.
    - _Tactic_: Credential Access.
    - _Technique_: Password Spraying.
    - _Procedure_: Running automated scripts using common passwords against exposed IoT management portals.
- **Root Cause**: The fundamental flaw, weakness, or vulnerability that enabled the security incident to occur.
- **False Positive**: A false alert where benign activity is incorrectly flagged as malicious.
- **False Negative**: A failure of security controls to detect or alert on actual malicious activity.

### 2. Incident Response Metrics

```
Attack Begins           Incident Detected           Incident Resolved
     |                          |                          |
     v                          v                          v
-----+--------------------------+--------------------------+-----> Time
     |                          |                          |
     +------ DWELL TIME --------+                          |
     |        (MTTD)            |                          |
     +--------------------------+--------- MTTR -----------+
```

- **Mean Time to Detect (MTTD)**: The average time required for an organization to discover a security incident after initial compromise.
- **Mean Time to Respond / Recover (MTTR)**: The average time taken to contain, eradicate, and fully restore systems after an incident is detected.
- **Dwell Time**: The total duration an attacker remains undetected inside an organization's environment (calculated from initial access to detection).

## NIST Incident Response Lifecycle (NIST SP 800-61 Rev. 2)

The NIST Incident Response Lifecycle is a structured four-phase framework designed to help organizations handle cybersecurity incidents.

```
                  +-----------------------------------+
                  |        1. PREPARATION             |
                  +-----------------+-----------------+
                                    |
                                    v
                  +-----------------+-----------------+
            +---->|   2. DETECTION & ANALYSIS         |<---+
            |     +-----------------+-----------------+    |
            |                       |                      |
            |                       v                      |
            |     +-----------------+-----------------+    |
            |     |   3. CONTAINMENT, ERADICATION     |    |
            |     |      & RECOVERY                   |----v
            |     +-----------------+-----------------+
            |                       |
            |                       v
            +-----------------------+-----------------+
                  |        4. POST-INCIDENT ACTIVITY  |
                  |           (Lessons Learned)       |
                  +-----------------------------------+
```

### Phase 1: Preparation

- **Policies, Plans, and Procedures**: Establishing clear definitions of incidents, organizational roles, levels of authority, SOPs, and metrics.
- **Asset Mapping & Baselining**: Maintaining up-to-date asset inventories, topological network diagrams, baseline functional profiles, and cryptographic file hashes.
- **Facility Setup & War Room**: Establishing centralized communication facilities, out-of-band communication methods (e.g., encrypted messaging, satellite phones), and dedicated incident handling hardware.
- **Jump Kit Assembly**: Preparing pre-configured, isolated toolkits containing:
    - Investigative laptops loaded with specialized analysis tools (packet sniffers, memory dumpers).
    - Digital forensics workstations and write-blockers.
    - Clean, blank storage media, crossover network cables, and physical evidence collection tools (chain-of-custody bags, security tape, hard-bound logs).

### Phase 2: Detection and Analysis

#### 1. Common Attack Vector Classifications

- **External/Removable Media**: Infection via malicious code on infected USB drives or peripherals.
- **Attrition**: Brute-force attacks or DDoS targeting authentication mechanisms or system bandwidth.
- **Web**: Attacks originating from web applications, cross-site scripting (XSS), or malicious redirects.
- **Email**: Phishing messages, malicious attachments, or social engineering links.
- **Impersonation**: Rogue access points, MitM attacks, spoofing, or SQL injection.
- **Improper Usage**: Internal policy violations committed by authorized users.
- **Loss or Theft of Equipment**: Missing laptops, mobile devices, or exposed IoT devices.

#### 2. Signs of an Incident: Precursors vs. Indicators

- **Precursor**: A sign indicating that an attack **may happen in the future**.
    - _Examples_: Web server access logs displaying automated vulnerability scans; announcements of zero-day exploits targeting installed software; extortion threats.
- **Indicator**: A sign indicating that an attack **is occurring now or has already occurred**.
    - _Examples_: Intrusion detection system (IDS) buffer overflow alerts; host antivirus malware notifications; unexpected modification of system files; unusual outbound network traffic spikes.

#### 3. Analysis Strategies & Methods

- **Baseline Profiling**: Comparing active network bandwidth, log frequencies, and system resource consumption against established normal patterns.
- **Event Correlation**: Cross-referencing disparate logs (e.g., matching source IP addresses from firewall logs with authenticated usernames in application logs) to validate incident legitimacy.
- **Data Filtering**: Applying filters to reduce high volumes of alerts and eliminate false positives.

#### 4. Incident Prioritization Criteria

Incidents must be prioritized based on impact rather than arrival order:

- **Functional Impact**: Extent of operational disruption (None, Low, Medium, High).
- **Information Impact**: Extent of data compromise (None, Privacy Breach, Proprietary Breach, Integrity Loss).
- **Recoverability**: Estimated time and effort required to restore operations (Extended, Predictable, Supplemented, Not Recoverable).

```
                      +-----------------------------+
                      | INCIDENT PRIORITIZATION     |
                      +--------------+--------------+
                                     |
         +---------------------------+---------------------------+
         |                           |                           |
+--------v--------+         +--------v--------+         +--------v--------+
| FUNCTIONAL      |         | INFORMATION     |         | RECOVERABILITY  |
| IMPACT          |         | IMPACT          |         |                 |
| Operational     |         | Privacy, Data   |         | Time/Cost to    |
| Disruption      |         | Exfiltration    |         | Restore         |
+-----------------+         +-----------------+         +-----------------+
```

### Phase 3: Containment, Eradication, and Recovery

```
+------------------+     +------------------+     +------------------+
|   CONTAINMENT    |     |   ERADICATION    |     |    RECOVERY      |
|  Stop the spread | --> | Remove root cause| --> | Restore systems  |
|  Isolate hosts   |     | Clean malware    |     | Patch flaws      |
+------------------+     +------------------+     +------------------+
```

#### 1. Containment Strategy Selection

Containing an incident prevents further damage while preserving evidence. Containment strategies must consider:

- Potential damage to and exfiltration of assets.
- Need to preserve digital evidence.
- Service availability requirements.
- Time and resource costs.
- Duration of the solution (temporary workaround vs. permanent fix).

#### 2. Attacking Host Identification

- Validating source IP addresses (checking for spoofing).
- Searching incident databases and threat intelligence feeds.
- Monitoring external communication channels (command-and-control servers).

#### 3. Eradication

Eliminating all components of the incident from the environment:

- Removing malware, webshells, and rogue applications.
- Disabling compromised user accounts.
- Mitigating exploited vulnerabilities across all affected devices.

#### 4. Recovery

Restoring systems to clean, operational state:

- Rebuilding hosts from secure baselines or clean backups.
- Installing security patches and changing compromised credentials.
- Hardening perimeter firewalls and network segmentation rules.
- Implementing enhanced monitoring and logging on restored assets.

### Phase 4: Post-Incident Activity (Lessons Learned)

Post-incident analysis helps organizations improve future security posture.

- **Timing**: Conduct a formal "Lessons Learned" meeting within a few days of incident resolution.
- **Key Questions to Answer**:
    - Exactly what happened, and at what timestamps?
    - How well did staff follow documented procedures? Were procedures adequate?
    - What information was needed sooner?
    - What steps inhibited recovery?
    - What corrective actions can prevent similar incidents in the future?
    - What precursors or indicators should be monitored in the future?

### Incident Response Team Models & Staffing Options

```
                    +-------------------------------+
                    |  INCIDENT RESPONSE TEAMS      |
                    +---------------+---------------+
                                    |
         +--------------------------+--------------------------+
         |                          |                          |
+--------v--------+        +--------v--------+        +--------v--------+
| CENTRALIZED     |        | DISTRIBUTED     |        | COORDINATING    |
| Single team for |        | Multiple teams  |        | Advisory body;  |
| whole enterprise|        | per division/loc|        | no authority    |
+-----------------+        +-----------------+        +-----------------+
```

- **Centralized IR Team**: A single, dedicated team handles security incidents across the entire organization.
- **Distributed IR Team**: Multiple regional or logical teams handle incidents for specific divisions or locations.
- **Coordinating Team**: A central authority that provides guidance and support to local response teams without direct operational control.
- **Staffing Frameworks**:
    - _In-House Employees_: Fully internal staff manage incident response.
    - _Partially Outsourced_: Internal staff handle daily operations and call contractors for severe incidents or specialized skills (e.g., deep digital forensics).
    - _Fully Outsourced_: External contractors manage all incident response operations.

## Digital Forensics for Incident Response

### 1. Fundamental Definition

**Digital Forensics**: The process of identifying, preserving, collecting, examining, analyzing, documenting, and reporting digital evidence to understand a security incident and support legal or administrative proceedings.

### 2. The 7-Step Digital Forensics Process

```
[1. IDENTIFICATION] -> [2. PRESERVATION] -> [3. COLLECTION] -> [4. EXAMINATION]
                                                                     |
[7. REPORTING]     <- [6. DOCUMENTATION] <- [5. ANALYSIS]   <--------+
```

1. **Identification**: Locate potential evidence sources (devices, logs, storage media, volatile memory, network traces).
2. **Preservation**: Protect physical and digital evidence from modification, tampering, or deletion (e.g., using write-blockers, creating bit-stream disk images).
3. **Collection**: Gather relevant evidence using standard, forensic techniques (e.g., capturing live RAM, copying log files).
4. **Examination**: Extract data using forensic tools to uncover hidden files, deleted artifacts, and system records.
5. **Analysis**: Correlate extracted evidence to reconstruct timelines, determine attack origin, and establish what occurred.
6. **Documentation**: Maintain records of all tools, actions, system outputs, and evidence handling throughout the investigation.
7. **Reporting**: Produce a formal report detailing findings, attack timelines, impacted systems, and forensic conclusions.

### 3. Evidence Types & Essential Tools

#### Key Forensic Artifacts

- **Volatile Data / Memory Snapshots**: Live RAM dumps capturing running processes, active network connections, and unencrypted credentials.
- **Network Traffic (PCAP)**: Recorded network packets capturing session data, communication protocols, and payload content.
- **System & Security Logs**: Event logs, firewall logs, web server logs, and authentication records.
- **Disk Images**: Bit-stream copies of non-volatile storage media.

#### Essential Forensic Software

|   |   |   |
|---|---|---|
|Tool|Category|Key Capabilities & Exam Applications|
|**Autopsy**|Disk Image Analysis / Hard Drive Forensics|• Graphical interface for analyzing disk images.<br>• Recovers deleted files and parses system artifacts.<br>• Performs keyword searches and hash matching.<br>• Extracts browser history, metadata, and timeline events.|
|**Wireshark**|Packet Sniffer / Protocol Analyzer|• Captures live network traffic and inspects saved PCAP files.<br>• Decodes network communication protocols.<br>• Identifies suspicious network traffic, cleartext credentials, and DoS floods.<br>• Reconstructs raw TCP sessions and streams.|

### 4. Chain of Custody Protocols

To ensure evidence is admissible in formal legal proceedings, investigators must maintain a complete, verifiable record of evidence handling.

**Every evidence record must detail**:

- Unique identifying information (serial numbers, model numbers, MAC addresses, IP addresses).
- Name, title, and contact details of every individual handling the evidence.
- Exact date, time, and timezone of each transfer.
- Secure physical or digital locations where evidence was stored.
- Signed transfer statements acknowledging receipt and custody.

## Exam Case Study Frameworks & Scenarios

Use this framework to analyze and structure responses to case study exam questions:

```
+-----------------------------------------------------------------------+
| STEP 1: ASSET & LAYER IDENTIFICATION                                  |
| Identify critical assets and map components to the 4-stage IoT layers.|
+-----------------------------------^-----------------------------------+
                                    |
+-----------------------------------v-----------------------------------+
| STEP 2: THREAT, VULNERABILITY & RISK MAPPING                          |
| Categorize Threat Actor, Vulnerabilities, Risk, and Incident type.    |
+-----------------------------------^-----------------------------------+
                                    |
+-----------------------------------v-----------------------------------+
| STEP 3: CIA TRIAD & SAFETY IMPACT EVALUATION                          |
| Determine impacted security principles (C, I, A, Safety).             |
+-----------------------------------^-----------------------------------+
                                    |
+-----------------------------------v-----------------------------------+
| STEP 4: IR LIFECYCLE & FORENSIC STEPS                                 |
| Outline Immediate Containment, Eradication, Recovery & Forensics.     |
+-----------------------------------^-----------------------------------+
                                    |
+-----------------------------------v-----------------------------------+
| STEP 5: RECOMMENDED LAYERED CONTROLS                                  |
| Propose defense-in-depth solutions across all affected layers.        |
+-----------------------------------------------------------------------+
```

### Exam Case Study 1: Smart Manufacturing Plant Incident

#### Scenario

An automated manufacturing plant uses temperature and pressure sensors that transmit data wirelessly to an edge gateway. The gateway pre-processes this data and forwards it to a cloud analytics platform, which sends control commands back to PLCs operating industrial machinery.

During operations, the monitoring dashboard shows normal temperature values. However, physical machinery begins operating at unsafe speeds, causing equipment damage and a production shutdown. Investigation reveals that the sensors are functioning properly, communication encryption is enabled, and the cloud platform is secure.

#### Solved Case Analysis

##### 1. Attack Pathway Analysis

- **Mechanism**: The attacker compromised the **Edge Gateway Layer**.
- **Execution**: While sensors measured accurate data and the channel was encrypted, the compromised gateway intercepted the valid sensor readings, replaced them with forged "normal" parameters, and sent them to the cloud. Simultaneously, the gateway injected elevated speed commands to the PLCs.
- **Why Encryption Failed**: The gateway was an authorized decryption point. Encryption protected the transport channel, but could not prevent data modification at the compromised processing node.

##### 2. Layer Mapping & Vulnerability Matrix

|   |   |   |
|---|---|---|
|Stage / Element|Architecture Layer|Specific Vulnerability / Flaw|
|Temperature/Pressure Monitoring|Perception/Sensing Layer|Lack of local cross-validation between sensors and physical machine speeds.|
|Transport Security|Network Layer|Blind trust in encrypted channels without endpoint payload validation.|
|Gateway Processing|Edge/Gateway Layer|Hardened access control failure, outdated patch levels, lack of hardware root-of-trust.|
|Analytics & Commands|Cloud/App Layer|Lack of automated sanity checks (e.g., cloud accepting normal temp reports while machine speed spikes).|
|Physical Execution|Actuation Layer|Absence of independent, hardware-enforced emergency shutoff interlocks.|

##### 3. Security Principle Impact Analysis

- **Integrity (Directly Affected)**: Sensor measurements and machine control parameters were modified.
- **Availability (Directly Affected)**: Equipment damage caused a production shutdown.
- **Safety (Directly Affected)**: Uncontrolled machine speeds created physical hazards for shop-floor personnel.
- **Confidentiality (Potentially Affected)**: System configuration settings may have been exposed during gateway compromise.

##### 4. Immediate Incident Response Plan

```
[1. CONTAINMENT] -> Disconnect Edge Gateway from network.
                    Switch PLCs to manual control.
                                 |
                                 v
[2. FORENSICS]   -> Capture live gateway RAM dump.
                    Pull Wireshark PCAPs and log files for Autopsy analysis.
                                 |
                                 v
[3. ERADICATION] -> Re-image gateway firmware from clean baseline.
                    Rotate all access keys and device credentials.
                                 |
                                 v
[4. RECOVERY]    -> Re-segment network (VLANs).
                    Deploy patch updates and verify integrity before reconnecting.
```

##### 5. Defense-in-Depth Architecture Solution

- **Sensing Layer**: Implement physical tamper protection and local peer-to-peer sensor validation.
- **Network Layer**: Enforce network segmentation (isolating OT networks from IT networks) and anti-replay timestamps.
- **Edge/Gateway Layer**: Deploy hardware Root-of-Trust (TPM), message authentication codes (HMAC), secure boot, and gateway integrity monitoring.
- **Application/Cloud Layer**: Implement sanity checks and anomaly detection algorithms to compare sensor data against actuator states.
- **Actuation Layer**: Install independent, physical safety relays that cut power if machinery exceeds safe operating thresholds.

### Exam Case Study 2: Smart Healthcare System Compromise

#### Scenario

A hospital deploys wearable IoT sensors to monitor patient heart rates, blood pressure, and oxygen levels. Data is sent wirelessly to a mobile gateway, processed by an edge server, and stored on a cloud system that alerts medical staff.

An attacker obtains a valid wearable device ID and injects false physiological data into the network. The system displays normal readings on clinician dashboards while a patient experiences medical distress.

#### Solved Case Analysis

##### 1. Security Flaw Analysis

- **Root Cause**: Relying on **Device Authentication alone** without verifying **Data Validity or Data Provenance**.
- **Impact**: Demonstrates that authenticating a device identity does not guarantee that the generated data is accurate or trustworthy.

##### 2. Layer Analysis & Attack Propagation

$\text{Attacker impersonates ID (Sensing)} \rightarrow \text{Forged data transmitted (Network)} \rightarrow \text{Edge passes data (Gateway)} \rightarrow \text{Cloud updates UI (Application)}$

- **Perception Layer**: Attacker uses a valid ID to format forged physiological payloads.
- **Network Layer**: The network forwards the forged packets because they use valid transport structures.
- **Edge/Gateway Layer**: The edge server accepts data based on the authenticated device ID, missing payload inconsistencies.
- **Application Layer**: Clinician dashboards present the false data, leading to incorrect medical decisions.

##### 3. CIA Triad Assessment

- **Integrity**: Primary point of failure—patient health metrics were altered.
- **Safety**: Primary real-world impact—patient health was placed at risk due to delayed medical intervention.
- **Confidentiality**: Secondary impact if the stolen device ID exposed patient identity records.

##### 4. Proposed Technical Solution & Controls

- **Zero-Trust Communication Architecture**: Never trust, always verify. Every data payload must undergo device authentication, cryptographic integrity checks, and contextual validity checks.
- **Data Provenance Implementation**: Attach cryptographic, time-stamped signatures to data at the sensor level, ensuring data origins can be traced and verified.
- **Multi-Layer Validation Strategy**:
    - _Edge Layer_: Run real-time algorithms to check for physiological impossibilities (e.g., heart rate jumping from 70 bpm to 200 bpm in one millisecond).
    - _Cloud Layer_: Cross-reference incoming wearable metrics against auxiliary sensors and historical patient baselines.

### Quick-Reference Formula Guide for Exam Prep

- **Risk** = $\text{Threat} \times \text{Vulnerability} \times \text{Impact}$
- **Dwell Time** = $\text{Detection Timestamp} - \text{Initial Compromise Timestamp}$
- **MTTD** = $$\frac{\text{Total Time Elapsed Before Detection Across Incidents}}{\text{Total Number of Incidents}}$$
- **MTTR** = $$\frac{\text{Total Time Spent Restoring Systems Across Incidents}}{\text{Total Number of Incidents}}$$