# Blue Team: Summary of Operations

## Table of Contents
- Network Topology
- Description of Targets
- Monitoring the Targets
- Patterns of Traffic & Behavior
- Suggestions for Going Further

### Network Topology
_TODO: Fill out the information below._

The following machines were identified on the network:
- Name of VM 1
  - **Operating System**: Capstone
  - **Purpose**: To host a Web server.
  - **IP Address**: 192.168.1.105
- Name of VM 2
  - **Operating System**: ELk
  - **Purpose**: Capture and Monitor systems logs for Capstone server
  - **IP Address**: 192.168.1.100

### Description of Targets
_TODO: Answer the questions below._

The target of this attack was: `Target 1` (192.168.1.110).

Target 1 is an Apache web server and has SSH enabled, so ports 80 and 22 are possible ports of entry for attackers. As such, the following alerts have been implemented:

### Monitoring the Targets

Traffic to these services should be carefully monitored. To this end, we have implemented the alerts below:

#### Name of Alert 1
_TODO: Replace `Alert 1` with the name of the alert._

Alert 1 is implemented as follows:
  - **Metric**: packetbeat
  - **Threshold**: Above 400
  - **Vulnerability Mitigated**: top 5 'http.response.status_code' IS ABOVE 400 FOR THE LAST 5 minutes
  - **Reliability**: high reliability.

#### Name of Alert 2
Alert 2 is implemented as follows:
  - **Metric**: packetbeat
  - **Threshold**: Above 3500
  - **Vulnerability Mitigated**:WHEN sum() of http.request.bytes OVER all documents IS ABOVE 3500 FOR THE LAST 1 minute
  - **Reliability**: medium
#### Name of Alert 3
Alert 3 is implemented as follows:
  - **Metric**: metricbeat
  - **Threshold**: Above 0.5
  - **Vulnerability Mitigated**: WHEN max() OF system.process.cpu.total.pct OVER all documents IS ABOVE 0.5 FOR THE LAST 5 minutes
  - **Reliability**: medium

_TODO Note: Explain at least 3 alerts. Add more if time allows._

### Suggestions for Going Further (Optional)
_TODO_:
- Each alert above pertains to a specific vulnerability/exploit. Recall that alerts only detect malicious behavior, but do not stop it. For each vulnerability/exploit identified by the alerts above, suggest a patch. E.g., implementing a blocklist is an effective tactic against brute-force attacks. It is not necessary to explain _how_ to implement each patch.

The logs and alerts generated during the assessment suggest that this network is susceptible to several active threats, identified by the alerts above. In addition to watching for occurrences of such threats, the network should be hardened against them. The Blue Team suggests that IT implement the fixes below to protect the network:
- Vulnerability 1
  - **Patch**: Use a Web Application Firewall(WAF)
  - **Why It Works**: WAFs can block suspicious login attempts coming from a single IP address
- Vulnerability 2
  - **Patch**: Add salt to all hashes/passwords
  - **Why It Works**: It'll add another layer of protection
- Vulnerability 3
  - **Patch**: Limit file access and block unused ports
  - **Why It Works**: All network ports should stay closed and should only be opened when needed for applications and services. Certain services come with configurations that require some ports open for communication through the API. 
