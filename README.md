# Path-Traversal

Solutions to the PortSwigger Web Security Academy Path Traversal (CWE-22) labs, featuring custom Python exploit scripts and step-by-step walkthroughs.

## About

Path traversal (also known as directory traversal) is a web security vulnerability that allows an attacker to read arbitrary files on the server running an application. By manipulating file path parameters with sequences like `../`, an attacker can escape the intended base directory and access sensitive data such as application source code, configuration files, credentials, and operating system files.

Each lab in this repository has its own dedicated folder containing:
- **Python Exploit Script:** A custom script that automates the HTTP request and payload delivery to solve the lab
- **Step-by-Step Walkthrough:** A detailed explanation covering the vulnerability mechanics, filter bypass techniques, and remediation strategies

## Labs

| # | Lab | Technique / Bypass | Status |
|---|-----|--------------------|--------|
| 1 | File path traversal, simple case | Basic `../` sequence |  |
| 2 | File path traversal, traversal sequences blocked with absolute path bypass | Absolute file path (`/etc/passwd`) | |
| 3 | File path traversal, traversal sequences stripped non-recursively | Nested traversal sequences (`....//`) |  |
| 4 | File path traversal, traversal sequences stripped with superfluous URL-decode | Double URL encoding (`%252e%252e%252f`) |  |
| 5 | File path traversal, validation of start of path | Retaining expected base folder (`/var/www/images/../../../etc/passwd`) | |
| 6 | File path traversal, validation of file extension with null byte bypass | Null byte injection (`%00.png`) |  |

## Key Takeaways & Prevention

- **Avoid passing user input directly to filesystem APIs:** Map user selections to hardcoded file identifiers or database indexes instead of raw filenames.
- **Canonicalize and validate paths:** Resolve the full canonical path on the server and verify that it starts with the expected base directory before opening the file.

## Disclaimer

This repository is created strictly for educational purposes and authorized security research. All exercises were performed within isolated PortSwigger Web Security Academy environments.

## Author
GlitchWH - (Waqas Hussain)
