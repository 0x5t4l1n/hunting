# Hunting

A comprehensive collection of security testing resources and payloads for bug bounty hunters, penetration testers, and security researchers.

## 📁 Repository Structure

### Vulnerability Payloads by Type
This repository contains a complete collection of testing payloads organized by vulnerability type.

**Injection Vulnerabilities:**
- **[SQL Injection](./SQL-Injection/)** - Database query manipulation
- **[NoSQL Injection](./NoSQL-Injection/)** - NoSQL database injection (MongoDB, Redis, CouchDB)
- **[XSS (Cross-Site Scripting)](./XSS/)** - Client-side code injection
- **[Command Injection](./Command-Injection/)** - OS command execution & symbolic link attacks
- **[SSTI (Server-Side Template Injection)](./SSTI/)** - Template engine exploitation & RCE
- **[SSJI (Server-Side JavaScript Injection)](./SSJI/)** - Node.js code injection & RCE
- **[CSV Injection](./CSV-Injection/)** - Formula injection in spreadsheets
- **[LDAP Injection](./LDAP-Injection/)** - Directory service manipulation
- **[Log Injection](./Log-Injection/)** - Log file manipulation
- **[XML Injection](./XML-Injection/)** - XML and XXE attacks
- **[Prompt Injection](./Prompt-Injection/)** - AI/LLM prompt manipulation

**Access Control Vulnerabilities:**
- **[Path Traversal](./Path-Traversal/)** - Directory traversal attacks
- **[IDOR](./IDOR/)** - Insecure direct object references
- **[Open Redirect](./Open-Redirect/)** - Unvalidated redirects

**Authentication & Authorization:**
- **[Authentication Bypass](./Authentication-Bypass/)** - Auth bypass techniques
- **[Password Reset](./Password-Reset/)** - Password reset vulnerabilities & account takeover
- **[Weak Passwords](./Weak-Passwords/)** - Common weak passwords and defaults

**Server-Side Vulnerabilities:**
- **[SSRF](./SSRF/)** - Server-side request forgery
- **[Deserialization](./Deserialization/)** - Insecure deserialization
- **[File Upload](./File-Upload/)** - Malicious file upload & RCE techniques
- **[Symbolic Link Attacks](./Symbolic-Link-Attacks/)** - Symlink exploitation & file system attacks
- **[Timing Attacks](./Timing-Attacks/)** - Side-channel timing analysis & user enumeration

**Configuration & Design:**
- **[Security Misconfiguration](./Security-Misconfiguration/)** - Default credentials, misconfigurations
- **[CORS Misconfiguration](./CORS-Misconfiguration/)** - Cross-origin resource sharing issues
- **[HTTP Request Smuggling](./HTTP-Request-Smuggling/)** - Request desynchronization attacks
- **[JWT Vulnerabilities](./JWT-Vulnerabilities/)** - JSON Web Token implementation flaws
- **[Business Logic](./Business-Logic/)** - Business logic flaws
- **[Weak Cryptography](./Weak-Cryptography/)** - Weak crypto implementations
- **[Vulnerable Components](./Vulnerable-Components/)** - Known vulnerable libraries

**Network & Anonymity:**
- **[Tor-Based Attacks](./Tor-Based-Attacks/)** - Tor anonymity exploitation & onion service testing

## 🎯 Purpose

This repository serves as a comprehensive reference for security professionals to:
- Test web applications for common vulnerabilities
- Learn about different attack vectors
- Prepare for bug bounty hunting
- Conduct authorized penetration testing
- Understand security risks in web applications

## ⚠️ Legal Disclaimer

**IMPORTANT**: All payloads and techniques in this repository are for **authorized testing only**. 

- ✅ Use on systems you own
- ✅ Use with explicit written permission
- ✅ Use in authorized bug bounty programs
- ✅ Use for educational purposes in controlled environments
- ❌ **NEVER** use on systems without authorization

Unauthorized testing is illegal and unethical. Always follow responsible disclosure practices.

## 🚀 Getting Started

1. Choose the vulnerability type you want to test from the list above
2. Navigate to the corresponding directory
3. Review the README.md for context and methodology
4. Use the payload files in your authorized testing

## 📚 Resources

- [OWASP Top 10 Official](https://owasp.org/www-project-top-ten/)
- [OWASP Testing Guide](https://owasp.org/www-project-web-security-testing-guide/)
- [Bug Bounty Platforms](https://www.bugcrowd.com/) | [HackerOne](https://www.hackerone.com/)

## 🤝 Contributing

Contributions are welcome! Please read our [Contributing Guidelines](./CONTRIBUTING.md) before submitting.

Quick guidelines:
- All content must be legal and ethical
- Payloads should be well-documented
- Follow existing structure and patterns
- Focus on educational value

For detailed information on how to contribute, see [CONTRIBUTING.md](./CONTRIBUTING.md).

## 🏆 Contributors

A huge thank you to all our amazing contributors! This project wouldn't be possible without your support. 🙏

See our [**Contributors Hall of Fame**](./CONTRIBUTORS.md) to view all contributors with their GitHub profiles!

All contributors are automatically recognized and added to our hall of fame when they contribute to this repository. ✨

## ⚖️ Legal Disclaimer

**IMPORTANT**: Read our [Legal Disclaimer](./DISCLAIMER.md) before using any content from this repository.

This repository is for **EDUCATIONAL AND AUTHORIZED TESTING PURPOSES ONLY**. Unauthorized access to computer systems is illegal.

## 📜 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

**Note**: While this repository is open source under the MIT License, all content is for educational and authorized testing purposes only. Please review our [Legal Disclaimer](./DISCLAIMER.md) before use.

---

**Happy Hunting! 🎯 Stay Ethical. Stay Legal.**

