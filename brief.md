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

## Cybersecurity

## Data

## Misconception in My Track

## Open Question
