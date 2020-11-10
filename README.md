# Security.





## Contents at a Glance.
* [About](#about)
* [Documentation.](#documentation)
* [Useful Links.](#useful-links)
* [Spring Security.](https://github.com/descriptions-of-it-technologies/spring-security)
* [Cross-Site Request Forgery. CSRF.](cross-site-request-forgery.md)
* [Cross-site Scripting Worm. XSS.](cross-site-scripting-worm.md)
* [Many Levels of Security.](#many-levels-of-security)
* [DNC Email Server.](#dnc-email-server)
* [Mitigating Actions.](#mitigating-actions)
* [DNC Email Server - Alternate Theory.](#dnc-email-server---alternate-theory)
* [Security Audit Frameworks / Certifications.](#security-audit-frameworks--certifications)
* [Common Terminology.](#common-terminology)
* [PCI DSS Requirements.](#pci-dss-requirements)
* [Other Best Practices.](#other-best-practices)
* [Common Web Vulnerabilities.](#common-web-vulnerabilities)
* [OWASP Top 10 Web Application Security Risks.](#owasp-top-10-web-application-security-risks)
* [Help](#help)





## About.





## Documentation.





## Useful Links.
* [Open Web Application Security Project. OWASP.](https://owasp.org)
* [Top 10 Web Application Security Risks](https://owasp.org/www-project-top-ten)
* [OWASP Cheat Sheet Series](https://cheatsheetseries.owasp.org/)
* [Cross Site Scripting Prevention Cheat Sheet.](https://cheatsheetseries.owasp.org/cheatsheets/Cross_Site_Scripting_Prevention_Cheat_Sheet.html)
* [Content Security Policy Cheat Sheet.](https://cheatsheetseries.owasp.org/cheatsheets/Content_Security_Policy_Cheat_Sheet.html)





## Many Levels of Security.
* In the context of computing, there are many levels of security:
* Hardware Security - prevent unauthorized code execution
* Operating System - access to the computer and actions you can take
* Database - access to the database and actions you can take
* Message Brokers - read / write access to message queues
* Network Security - wifi, VPCs, etc
* Application Security - Access to the application and actions within application





## DNC Email Server.
* US Intelligence believes the hacked emails were obtained by Russian hackers via a cyberattack.
  * What does this mean?
    * Hackers obtained access to the DNC server via the internet to copy files from the server.
  * Mitigating Actions.
    * OS Patching to prevent known exploits - Unpatched Windows XP has about 8 minutes when exposed on the internet.
    * Password Length / Complexity requirements.





## Mitigating Actions.
* Don’t use common passwords!
* Firewalls - Only expose necessary ports to internet
* Prevent direct sign-on to super user accounts
* Use OS Level security features to restrict access
* Read access to email data files should be highly restricted
* Physical Security - Place Servers in secure rooms which require badge access at a minimum
  * Limit number of people, log access to room
  * Video security
* Personal Security - Only people who need access to the server should have access
  * ie - an email administrator, might not need physical access to the server
* Segregation of Duties - People should have roles and limited access for those roles
  * ie - department managers should not have super user accounts 
* End User Education about risk of phishing attacks
* 2FA - Two Factor Authentication to help confirm identity
* Don’t use Gmail for official business - corporate email systems can enforce a variety of security policies
  * Yes, Google Apps for Business can do this - its a matter of policy enforcement
* Threat scanning of incoming emails
* Password expiration policies
* №1 Mitigating Action would have been to use the State Department’s email
* A 45,000 person organization will have more specialized resources
* Accounts indicate the Clinton email server was setup by a Clinton aide.
  * It is likely the aide did not have the training nor experience to configure and secure the server
* Unlikely server was patched on a regular schedule
* Unlikely network security in place
* Unlikely to have physical security or segregation of duties





## DNC Email Server - Alternate Theory.
* There is a theory that challenges the official conclusion based on file timestamps the email data files were copied to a USB drive
* What does this mean?
  * Hacker had physical access to the DNC Email Server
  * Likely an employee with a sign-on
* Plausible theory, since a lot of data breaches do happen this way





## Security Audit Frameworks / Certifications
* PCS-DSS - Payment Card Industry Data Security Standard
* Applicable if your organization processes credit / debit cards
* SOX - Sarbanes-Oxley
* For US based publicly traded companies
* HIPAA - Health Insurance Portability and Accountability Act
* US Based Medical Industry
* SSAE 16 - Statement on Standards for Attestation Engagements (SSAE) No. 16
* CPA - authoritative guidance for reporting on service organizations





## Common Terminology
* PII - Personally Identifiable Information - name, address, email, tax ids, etc
* Encryption at Rest - Sensitive data needs to be encrypted when stored (database, filesystem,backup tapes, etc)
* Encryption in Flight - When transmitted, sensitive data needs to be encrypted - can be protocol(https, ssh, etc)
* Segregation of Duties - Avoid having powerful super users in organization
* Processes and Controls - Be able to document compliance (source control, issue management)





## PCI DSS Requirements
1. Protect System with Firewalls
2. Configure Passwords and Settings - Don’t use defaults
3. Protect Stored Cardholder Data - Use Industry accepted algorithms, don’t roll your own!
4. Encrypt Transmission of Cardholder Data across open, public networks
5. Use and update anti-virus software
6. Regularly update and patch systems
7. Restrict access to card holder data by business need to know
8. Assign Unique Id to each person with computer access
9. Restrict physical access to workplace and cardholder data
10. Implement logging and log management
11. Conduct vulnerability scans and penetration tests
12. Documentation and risk assessments





## Other Best Practices
* Use OS Service Accounts for Applications
* Service accounts should have minimal access needed
* Use database Service Accounts with minimal access
* Application account should not have access to alter or drop database tables
* Use layers of network security to protect internal systems
* ie - should not be able to reach database server from internet edge
* VPCs, VPNs, multiple physical networks





## Common Web Vulnerabilities:
* OWASP - Open Web Application Security Project - https://owasp.org
  * Nonprofit organization working to improve the security of software
  * Provides:
    * Tools and Resources
    * Community and Networking
    * Education and Training
* OWASP Top 10 Web Application Security Risks





## OWASP Top 10 Web Application Security Risks:
1. Injection - Injection of malicious code, such as SQL Injection attacks
   * Mitigation typically using proper encoding and bind variables
2. Broken Authentication - Authentication and session management implemented incorrectly
   * Mitigation - Use framework, don’t roll your own
3. Sensitive Data Exposure - Not protecting sensitive data
   * Mitigation - Proper error handling, don’t expose stack traces
4. XML External Entities- Poorly Configured XML Processors
   * Mitigation - Patch XML Processors frequently
5. Broken Access Control - User Restrictions not properly enforced
   * Mitigation - Automated Testing, verify restrictions
6. Security Misconfiguration - Unintentionally not protecting resources
   * Mitigation - Security Audits
7. CrossSite Scripting - XSS Allows Users to inject HTML or Javascript
   * Mitigation - Use proper validation and escaping
8. Insecure Deserialization - Insecure deserialization can allow remote code execution
   * Mitigation - Use open source, patch frequently
9. Using Components with Known Vulnerabilities - Popular components often have known vulnerabilities
   * Mitigation - Patch frequently
10. Insufficient Logging & Monitoring - Time to detect breaches often over 200 days
    * Mitigation - Properly monitor systems
    * Further information available on OWASP
    * Highly recommended reviewing
    




## Help.
