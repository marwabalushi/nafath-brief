Version: NAFATH-V4 
Track: Networking

## Overview
Modern software supply chains involve more than writing code. They include external libraries, development tools, AI systems, mobile applications, network infrastructure, and data dependencies. Each component can introduce security risks if it is not properly managed. Software teams must protect configuration secrets and verify third-party dependencies. AI systems require protection against malicious inputs and manipulated training data, while mobile applications need secure storage and communication. Networking plays an important role because attacks on internet routing can redirect traffic or disrupt access to essential services. Cybersecurity practices help identify and address vulnerabilities such as Log4Shell, which affected widely used software components. Data transparency tools, including Software Bills of Materials (SBOMs), help organizations understand their dependencies and respond to security incidents. Together, these practices improve software supply chain security.

## Software
The Twelve-Factor App recommends keeping configuration, including credentials and service settings, separate from application code. Environment variables allow developers to manage these values across different deployments without modifying the source code. This reduces the risk of accidentally exposing sensitive credentials in public repositories. However, environment variables must still be protected through appropriate access controls and secure secret management practices.

Resource: The Twelve-Factor App: Config -https://12factor.net/config

## AI
AI systems face security threats throughout their lifecycle. Data poisoning occurs when attackers manipulate training data to influence model behavior, while evasion attacks use specially crafted inputs to cause incorrect predictions. These threats can reduce the reliability of AI systems and affect downstream applications. MITRE ATLAS documents adversarial techniques against AI systems, helping security teams understand attack patterns and improve their defensive testing strategies.

Resource: MITRE ATLAS - https://atlas.mitre.org/

## Mobile
OWASP MASVS provides security requirements for mobile applications, covering areas such as secure data storage, cryptography, authentication, network communication, and code quality. These requirements help developers identify weaknesses and establish consistent security expectations. For example, protecting sensitive information stored on a device and securing communication with backend services can reduce data exposure. MASVS also supports structured mobile application security assessments.

Resource: OWASP Mobile Application Security Verification Standard (MASVS) - https://mas.owasp.org/MASVS/

## Networking
BGP route hijacking occurs when an unauthorized network announces IP prefixes belonging to another network, potentially redirecting internet traffic through the wrong path. RPKI helps reduce this risk by using digitally signed Route Origin Authorizations (ROAs) to verify whether an Autonomous System is authorized to originate a prefix. However, RPKI origin validation does not verify the entire AS path, so it cannot prevent every routing attack.

Resource: RFC 6811: BGP Prefix Origin Validation - https://www.rfc-editor.org/rfc/rfc6811

## Cybersecurity
Log4Shell (CVE-2021-44228) was a critical vulnerability in Apache Log4j, a widely used Java logging library. Attackers could exploit unsafe JNDI lookups through specially crafted log messages, potentially executing malicious code remotely. It was extremely severe because exploitation could be possible without authentication and many applications depended on Log4j. Apache addressed the vulnerability through security updates, initially in version 2.15.0, followed by additional fixes in later releases.

Resource: Apache Logging Services: Security - https://logging.apache.org/security.html

## Data
A Software Bill of Materials (SBOM) is a structured inventory of software components and their dependencies. It helps organizations identify which libraries and versions are included in their applications, making vulnerability management more effective. According to NTIA, the minimum data fields include supplier name, component name, component version, other unique identifiers, dependency relationships, SBOM data author, and timestamp. These details improve transparency and help security teams respond when vulnerable components are discovered.

Resource: NTIA: The Minimum Elements For a Software Bill of Materials (SBOM) - https://www.ntia.gov/report/2021/minimum-elements-software-bill-materials-sbom

## Misconception in My Track
A common misconception in networking is that deploying RPKI completely prevents BGP hijacking. In reality, RPKI-based Route Origin Validation only checks whether an Autonomous System is authorized to originate an IP prefix. It does not validate the complete AS path or prevent every routing attack. For example, an attacker may forge a route that includes a legitimate origin AS. RFC 6811 explains these limitations in Section 6, Security Considerations. Therefore, RPKI is an important security improvement, but network operators still need additional routing security measures.

Resource: RFC 6811: BGP Prefix Origin Validation - https://www.rfc-editor.org/rfc/rfc6811

## Open Question
How can network operators combine RPKI with other routing security mechanisms to detect and prevent BGP hijacking attacks that cannot be stopped by origin validation alone?
