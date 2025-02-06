# Career Knowledge

A melting-pot of theory useful for several career-paths

## SOC Team

* SOC Analyst (Level 1): Anything detected by the security solution would pass through these analysts first. These are the first responders to any detection. SOC Level 1 Analysts perform basic alert triage to determine if a specific detection is harmful. They also report these detections through proper channels.
* SOC Analyst (Level 2): While Level 1 does the first-level analysis, some detections may require deeper investigation. Level 2 Analysts help them dive deeper into the investigations and correlate the data from multiple data sources to perform a proper analysis.
* SOC Analyst (Level 3): Level 3 Analysts are experienced professionals who proactively look for any threat indicators and support in the incident response activities. The critical severity detection reported by Level 1 and Level 2 Analysts are often security incidents that need detailed responses, including containment, eradication, and recovery. This is where Level 3 analysts’ experience comes in handy.
* Security Engineer: All analysts work on security solutions. These solutions need deployment and configuration. Security Engineers deploy and configure these security solutions to ensure their smooth operation.
* Detection Engineer: Security rules are the logic built behind security solutions to detect harmful activities. Level 2 and 3 Analysts often create these rules, while the SOC team can sometimes also utilize the detection engineer role independently for this responsibility.
* SOC Manager: The SOC Manager manages the processes the SOC team follows and provides support. The SOC Manager also remains in contact with the organization’s CISO (Chief Information Security Officer) to provide him with updates on the SOC team’s current security posture and efforts.

## Forensics Methodology

* Collection: The first phase of digital forensics is data collection. Identifying all the devices from which the data can be collected is essential. Usually, an investigator can find personal computers, laptops, digital cameras, USBs, etc., on the crime scene. It is also necessary to ensure the original data is not tampered with while collecting the evidence and to maintain a proper document containing the collected items’ details. We will also be discussing the evidence-acquisition procedures in the upcoming tasks.
* Examination: The collected data may overwhelm investigators due to its size. This data usually needs to be filtered, and the data of interest needs to be extracted. For example, as an investigator, you collected all the media files from a digital camera on the crime scene. You may only require some of the media as you are concerned with the media recorded on a specific date and time. So, in the examination phase, you would filter the media files of the required time and move them to the next phase. Similarly, you may only need the data of a specific user from a system containing numerous user accounts. The examination phase helps you filter this particular data for analysis.
* Analysis: This is a critical phase. The investigators now have to analyze the data by correlating it with multiple pieces of evidence to draw conclusions. The analysis depends upon the case scenario and available data. The analysis aims to extract the activities relevant to the case chronologically.
* Reporting: In the last phase of digital forensics, a detailed report is prepared. This report contains the investigation’s methodology and detailed findings from the collected evidence. It may also contain recommendations. This report is presented to law enforcement and executive management. It is important to include executive summaries as part of the report, considering the level of understanding of all the receiving parties.

## Types of Forensic

* Computer forensics: The most common type of digital forensics is computer forensics, which concerns investigating computers, the devices most commonly used in crimes.
* Mobile forensics: Mobile forensics involves investigating mobile devices and extracting evidence such as call records, text messages, GPS locations, and more.
* Network forensics: This area of forensics covers investigation beyond individual devices. It includes the whole network. The majority of the evidence found in networks is the network traffic logs.
* Database forensics: Many critical data is stored in dedicated databases. Database forensics investigates any intrusion into these databases that results in data modification or exfiltration.
* Cloud forensics: Cloud forensics is the type of forensics that involves investigating data stored on cloud infrastructure. This type of forensics sometimes gets tricky for the investigators as there is little evidence on cloud infrastructures.
* Email forensics: Email, the most common communication method between professionals, has become an important part of digital forensics. Emails are investigated to determine whether they are part of phishing or fraudulent campaigns.

## Chain of Custody

* Description of the evidence (name, type).
* Name of individuals who collected the evidence.
* Date and time of evidence collection.
* Storage location of each piece of evidence.
* Access times and the individual record who accessed the evidence.

## Windows Forensics

* Disk image: The disk image contains all the data present on the storage device of the system (HDD, SSD, etc.). This data is non-volatile, meaning that the disk data would survive even after a restart of the operating system. For example, all the files like media, documents, internet browsing history, and more.
* Memory image: The memory image contains the data inside the operating system’s RAM. This memory is volatile, meaning the data will get lost after the system is powered off or restarted. For example, to capture open files, running processes, current network connections, etc., the memory image should be prioritized and taken first from the suspect’s operating system; otherwise, any restart or shutdown of the system would result in all the volatile data getting deleted. While carrying out digital forensics on a Windows operating system, disk and memory images are very important to collect.
* FTK Imager: FTK Imager is a widely used tool for taking disk images of Windows operating systems. It offers a user-friendly graphical interface for creating the image in various formats. This tool can also analyze the contents of a disk image. It can be used for both acquisition and analysis purposes.
* Autopsy: Autopsy is a popular open-source digital forensics platform. An investigator can import an acquired disk image into this tool, and the tool will conduct an extensive analysis of the image. It offers various features during image analysis, including keyword search, deleted file recovery, file metadata, extension mismatch detection, and many more.
* DumpIt: DumpIt offers the utility of taking a memory image from a Windows operating system. This tool creates memory images using a command-line interface and a few commands. The memory image can also be taken in different formats.
* Volatility: Volatility is a powerful open-source tool for analyzing memory images. It offers some extremely useful plugins. Each artifact can be analyzed using a specific plugin. This tool supports various operating systems, including Windows, Linux, macOS, and Android.

## Types of Incidents

* Malware Infections: Malware is a malicious program that can damage a system, network, or application. The majority of incidents are associated with malware infections.  There are different types of malware, each with a unique potential to cause damage. Malware infections are mostly caused by files that can be text, documents, executables, etc.
* Security Breaches: Security Breaches arise when an unauthorized person gets access to confidential data (something we don’t want them to see or have). Security Breaches are of the utmost importance as many businesses rely on their confidential data, which must only be accessible to authorized personnel.
* Data Leaks: Data leaks are incidents in which confidential information of an individual or an organization is exposed to unauthorized entities. Many attackers use data leaks for reputational damage to their victims or use this technique to threaten their victims and get what they need from them. Unlike Security Breaches, data leaks can also be unintentionally caused by human errors or misconfigurations.
* Insider Attacks: Incidents from within an organization are known as insider attacks. Think about a disgruntled employee infecting the whole network through a USB on his last day. This is an example of an insider attack. Someone within your organization intentionally initiating an attack comes under this category. These attacks can be hazardous, as an insider always has greater access to resources than an outsider.
* Denial Of Service Attacks: Availability is one of the three pillars of cyber security. Defensive security solutions and people constantly find ways to protect information; they ensure that the data is available to the people simultaneously. This is because there is no point in protecting something that is unavailable to us. Denial of Service attacks, or DoS attacks, are incidents where the attacker floods a system/network/application with false requests, eventually making it unavailable to legitimate users. This happens due to the exhaustion of resources available to entertain the requests.

## Incident Response Process

* Preparation: This is the first phase. The preparation phase includes building the necessary resources to handle an incident. These resources include developing incident response teams, having a proper incident response plan in place, and deploying necessary security solutions to combat the incidents.
* Identification: The identification phase refers to looking for any abnormal behavior that may indicate an incident. This involves using various security solutions and techniques to monitor abnormal events.
* Containment: Once an incident has been identified, the next step should be to contain it. This means minimizing the impact of the attack. This is usually done by isolating the victim machine, disabling the compromised user accounts, etc.
* Eradication: This phase, as its name suggests, involves removing the threat from the attacked environment. The threat may be of any kind. The eradication phase will ensure the subject environment is clean, and now we can move to the recovery phase.
* Recovery: The recovery phase is very important in this chain. It involves recovering the affected systems from backup or rebuilding them. The recovered systems are then tested and are ready to use.
* Lessons Learned: This is also an important part of the incident response lifecycle. Gaps in the detection and analysis of the incident are identified and documented, helping to improve the overall process in future incidents.

## Use Cases of Logs

* Security Events Monitoring: Logs help us detect anomalous behavior when real-time monitoring is used.
* Incident Investigation and Forensics: Logs are the traces of every kind of activity. It offers detailed information on what happened during the incident. The security team utilizes the logs to perform root cause analysis of incidents.
* Troubleshooting: As the logs also record the errors in systems or applications, they can be used to diagnose issues and helpful in fixing them.
* Performance Monitoring: Logs can also provide valuable insights into the performance of applications.
* Auditing and Compliance: Logs play a major role in Auditing and Compliance, making it easier with its capability to establish a trail of different kinds of activities.

## Types of Logs

* System Logs: The system logs can be helpful in troubleshooting running issues in the OS. These logs provide information on various operating system activities.
* Security Logs: The security logs help detect and investigate incidents. These logs provide information on the security-related activities in the system.
* Application Logs: The application logs contain specific events related to the application. Any interactive or non-interactive activity happening inside the application will be logged here.
* Audit Logs: The Audit logs provide detailed information on the system changes and user events. These logs are helpful for compliance requirements and can play a vital role in security monitoring as well.
* Network Logs: Network logs provide information on the network’s outgoing and incoming traffic. They play crucial roles in troubleshooting network issues and can also be handy during incident investigations.
* Access Logs: The Access logs provide detailed information about the access to different resources. These resources can be of different types, providing us with information on their access.

## Some Important Event IDs in Windows Operating System

* 4624: A user account successfully logged in
* 4625: A user account failed to login
* 4634: A user account successfully logged off
* 4720: A user account was created
* 4724: An attempt was made to reset an account’s password
* 4722: A user account was enabled
* 4725: A user account was disabled
* 4726: A user account was deleted

## Types of Firewall

* Stateless firewalls
    * Basic filtering
    * No track of previous connections
    * Efficient for high-speed networks
* Stateful firewalls
    * Recognize traffic by patterns
    * Complex rules can be applicable
    * Monitor the network connections
* Proxy firewalls
    * Inspect the data inside the packets as well
    * Provides content filtering options
    * Provides application control
    * Decrypts and inspects SSL/TLS data packets
* Next-generation firewalls
    * Provides advanced threat protection
    * Comes with an intrusion prevention system
    * Identify anomalies based on heuristic analysis
    * Decrypts and inspects SSL/TLS data packets

## Penetration Tester

* Types of hacker
    * White hat - These hackers are considered the "good people". They remain within the law and use their skills to benefit others
    * Grey hat - These people use their skills to benefit others often; however, they do not respect/follow the law or ethical standards at all times
    * Black hatWhite Hat - These people are criminals and often seek to damage organisations or gain some form of financial benefit at the cost of others

* Rules of Engagement
    * Permission - This section of the document gives explicit permission for the engagement to be carried out. This permission is essential to legally protect individuals and organisations for the activities they carry out.
    * Test Scope - This section of the document will annotate specific targets to which the engagement should apply. For example, the penetration test may only apply to certain servers or applications but not the entire network.
    * Rules - The rules section will define exactly the techniques that are permitted during the engagement. For example, the rules may specifically state that techniques such as phishing attacks are prohibited, but MITM (Man-in-the-Middle) attacks are okay.

* Methodology
    * Information Gathering - This stage involves collecting as much publically accessible information about a target/organisation as possible, for example, OSINT and research.
        * Note: This does not involve scanning any systems.
    * Enumeration/Scanning - This stage involves discovering applications and services running on the systems. For example, finding a web server that may be potentially vulnerable.
    * Exploitation - This stage involves leveraging vulnerabilities discovered on a system or application. This stage can involve the use of public exploits or exploiting application logic.
    * Privilege Escalation- - Once you have successfully exploited a system or application (known as a foothold), this stage is the attempt to expand your access to a system. You can escalate horizontally and vertically, where horizontally is accessing another account of the same permission group (i.e. another user), whereas vertically is that of another permission group (i.e. an administrator).
    * Post-exploitation - This stage involves a few sub-stages:
    	1. What other hosts can be targeted (pivoting)
        2. What additional information can we gather from the host now that we are a privileged user
        3. Covering your tracks
        4. Reporting

* Base
    * Black-Box Testing
        * This testing process is a high-level process where the tester is not given any information about the inner workings of the application or service.
        * The tester acts as a regular user testing the functionality and interaction of the application or piece of software. This testing can involve interacting with the interface, i.e. buttons, and testing to see whether the intended result is returned. No knowledge of programming or understanding of the programme is necessary for this type of testing.
        * Black-Box testing significantly increases the amount of time spent during the information gathering and enumeration phase to understand the attack surface of the target.
    * Grey-Box Testing
        * This testing process is the most popular for things such as penetration testing. It is a combination of both black-box and white-box testing processes. The tester will have some limited knowledge of the internal components of the application or piece of software. Still, it will be interacting with the application as if it were a black-box scenario and then using their knowledge of the application to try and resolve issues as they find them.
        * With Grey-Box testing, the limited knowledge given saves time, and is often chosen for extremely well-hardened attack surfaces.
    * White-Box Testing
        * This testing process is a low-level process usually done by a software developer who knows programming and application logic. The tester will be testing the internal components of the application or piece of software and, for example, ensuring that specific functions work correctly and within a reasonable amount of time.
        * The tester will have full knowledge of the application and its expected behaviour and is much more time consuming than black-box testing. The full knowledge in a White-Box testing scenario provides a testing approach that guarantees the entire attack surface can be validated.

## Main Principles

* CIA
    * Confidentiality
        * This element is the protection of data from unauthorized access and misuse. Organisations will always have some form of sensitive data stored on their systems. To provide confidentiality is to protect this data from parties that it is not intended for.
        * There are many real-world examples for this, for example, employee records and accounting documents will be considered sensitive. Confidentiality will be provided in the sense that only HR administrators will access employee records, where vetting and tight access controls are in place. Accounting records are less valuable (and therefore less sensitive), so not as stringent access controls would be in place for these documents. Or, for example, governments using a sensitivity classification rating system (top-secret, classified, unclassified)
    * Integrity
        * The CIA triad element of integrity is the condition where information is kept accurate and consistent unless authorized changes are made. It is possible for the information to change because of careless access and use, errors in the information system, or unauthorized access and use. In the CIA triad, integrity is maintained when the information remains unchanged during storage, transmission, and usage not involving modification to the information. Steps must be taken to ensure data cannot be altered by unauthorised people (for example, in a breach of confidentiality).
        * Many defences to ensure integrity can be put in place. Access control and rigorous authentication can help prevent authorized users from making unauthorized changes. Hash verifications and digital signatures can help ensure that transactions are authentic and that files have not been modified or corrupted.
    * Availability
        * In order for data to be useful, it must be available and accessible by the user.

* STRIDE
    * Spoofing  
        * This principle requires you to authenticate requests and users accessing a system. Spoofing involves a malicious party falsely identifying itself as another.
        * Access keys (such as API keys) or signatures via encryption helps remediate this threat.
    * Tampering   
        * By providing anti-tampering measures to a system or application, you help provide integrity to the data. Data that is accessed must be kept integral and accurate.
        * For example, shops use seals on food products.
    * Repudiation
        * This principle dictates the use of services such as logging of activity for a system or application to track.
    * Information Disclosure
        * Applications or services that handle information of multiple users need to be appropriately configured to only show information relevant to the owner.
    * Denial of Service
        * Applications and services use up system resources, these two things should have measures in place so that abuse of the application/service won't result in bringing the whole system down.
    * Elevation of Privilege
        * This is the worst-case scenario for an application or service. It means that a user was able to escalate their authorization to that of a higher level i.e. an administrator. This scenario often leads to further exploitation or information disclosure.

* Incident Response
    * Preparation
        * Do we have the resources and plans in place to deal with the security incident?
    * Identification
        * Has the threat and the threat actor been correctly identified in order for us to respond to?
    * Containment
        * Can the threat/security incident be contained to prevent other systems or users from being impacted?
    * Eradication
        * Remove the active threat.
    * Recovery
        * Perform a full review of the impacted systems to return to business as usual operations.
    * Lessons
        * Learned What can be learnt from the incident? I.e. if it was due to a phishing email, employees should be trained better to detect phishing emails.

## Confidentiality

* Something you know: Passwords or passphrases
* Something you have: Tokens, memory cards, smart cards
* Something you are: Biometrics, measurable characteristics

## Risk Management Terminology

* An asset: is something in need of protection.
* A vulnerability: is a gap or weakness in those protection efforts.
* A threat: is something or someone that aims to exploit a vulnerability to thwart protection efforts.

* Who is responsible for determining risk tolerance in an organization?
    * Executive management and board of directors

## Governance Elements

* Procedures are the detailed steps to complete a task that support departmental or organizational policies.
* Policies are put in place by organizationalgovernance, such as executive management, to provide guidance in all activities to ensure that the organization supports industry standards and regulations.
* Standards are often used by governance teams to provide a framework to introduce policies and procedures in support of regulations.
* Regulations are commonly issued in the form of laws, usually from government (not to be confused with governance) and typically carry financial penalties for non-compliance.

## Risk Treatment

* Risk avoidance is the attempt to eliminate the risk entirely. This could include ceasing operation for some or all of the activities of the organization that leave it exposed to a particular risk. Leadership may choose risk avoidance if the potential impact of a given risk is too high or if the likelihood of the risk being realized is simply too great.
* Risk acceptance is taking no action to reduce the likelihood of a risk occurring. Management may opt to conduct the business function associated with the risk without any further action on the part of the organization, either because the impact or likelihood of occurrence is negligible or because the benefit is more than enough to offset that risk.
* Risk mitigation is the most common type of risk management and includes taking actions to prevent or reduce the possibility of a risk event or its impact. Mitigation can involve remediation measures such as security controls, policies, procedures, and standards to minimize adverse risk. Risk cannot always be mitigated, but mitigations such as safety measures should always be in place.
* Risk transference is the practice of passing the risk to another party who will accept the financial impact of the harm resulting from a risk being realized in exchange for payment. Typically, this is an insurance policy.

## Security Controls

* Physical controls address security needs using physical hardware devices, such as badge readers, architectural features of buildings and facilities, and specific security actions taken by staff.
* Technical controls (also called logical controls) are security controls that computer systems and networks directly implement.
* Administrative controls (also known as managerial controls) are directives, guidelines, or advisories aimed at the people within the organization. They provide frameworks, constraints, and standards for human behavior and should cover the entire scope of the organization’s activities and its interactions with external parties and stakeholders.

## Incident Terminology

* Breach: The loss of control, compromise, unauthorized disclosure, unauthorized acquisition, or any similar occurrence where: a person other than an authorized user accesses or potentially accesses personally identifiable information; or an authorized user accesses personally identifiable information for other than an authorized purpose.
* Event: Any observable occurrence in a network or system.
* Exploit: A particular attack. It is named this way because these attacks exploit system vulnerabilities.
* Incident: An event that actually or potentially jeopardizes the confidentiality, integrity, or availability of an information system or the information the system processes, stores, or transmits.
* Intrusion: A security event, or combination of events, that constitutes a deliberate security incident in which an intruder gains, or attempts to gain, access to a system or system resource without authorization.
* Threat: Any circumstance or event with the potential to adversely impact organizational operations (including mission, functions, image, or reputation), organizational assets, individuals, other organizations, or the nation through an information system via unauthorized access, destruction, disclosure, modification of information, and/or denial of service. 
* Vulnerability: Weakness in an information system, system security procedures, internal controls, or implementation that could be exploited by a threat source.
* Zero Day: A previously unknown system vulnerability with the potential of exploitation without risk of detection or prevention because it does not, in general, fit recognized patterns, signatures, or methods.

## Components of the Incident Response Plan

* Preparation:
    * Develop a policy approved by management.
    * Identify critical data and systems and any single points of failure.
    * Train staff on incident response.
    * Implement an incident response team.
    * Practice Incident Identification (first response).
    * Identify roles and responsibilities.
    * Plan the coordination of communication between stakeholders.
    * Consider the possibility that a primary method of communication may not be available.
* Detection and Analysis:
    * Monitor all possible attack vectors.
    * Analyze the incident using known data and threat intelligence.
    * Prioritize incident response.
    * Standardize incident documentation.
* Containment
    * Gather evidence.
    * Choose an appropriate containment strategy.
    * Identify the attacker.
    * Isolate the attack.
* Post-Incident Activity
    * Identify evidence that may need to be retained.
    * Document lessons learned.

## Components of a Disaster Recovery Plan

* Executive summary providing a high-level overview of the plan
* Department-specific plans
* Technical guides for IT personnel responsible for implementing and maintaining critical backup systems
* Full copies of the plan for critical disaster recovery team members
* Checklists for certain individuals:
    * Critical disaster recovery team members will have checklists to help guide their actions amid the chaotic atmosphere of a disaste.
    * IT personnel will have technical guides helping them get the alternate sites up and running.
    * Managers and public relations personnel will have simple-to-follow, high-level documents to help them communicate the issue accurately without requiring imput from team members who are busy working on the recovery.