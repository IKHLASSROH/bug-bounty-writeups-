# Lab 02 - Source Code Disclosure via phpinfo()

## Category

Information Disclosure

## Difficulty

Apprentice

## Objective

Identify sensitive information exposed through a publicly accessible `phpinfo()` page.

---

## Tools Used

- Browser
- Feroxbuster
- SecLists (GitHub Wordlists)
- PortSwigger Web Security Academy

---

## Methodology

1. Explored the target application manually.
2. Used **Feroxbuster** to perform directory enumeration.
3. Used the **SecLists** `common.txt` wordlist from GitHub to discover hidden files and directories.
4. Found an exposed `phpinfo()` page.
5. Inspected the PHP configuration and environment variables.
6. Identified sensitive information required to complete the lab.
7. Submitted the discovered value and successfully solved the lab.

---

## Vulnerability

The application exposed a publicly accessible `phpinfo()` page containing sensitive server information.

The page disclosed details including:

- PHP version
- Loaded modules
- Server configuration
- Environment variables
- Internal file paths

This information should never be accessible to unauthenticated users.

---

## Security Impact

Information disclosure can help attackers:

- Fingerprint the target environment
- Identify outdated PHP versions
- Discover enabled extensions
- Reveal sensitive environment variables
- Collect information useful for future attacks

---

## Mitigation

- Remove `phpinfo()` pages from production environments.
- Restrict access to debugging pages.
- Protect sensitive environment variables.
- Perform regular security reviews to detect exposed files.

---

## What I Learned

This lab taught me how attackers use directory enumeration with **Feroxbuster** and **SecLists** to discover hidden resources. I also learned that debugging pages like `phpinfo()` can unintentionally expose valuable information that may increase the attack surface of a web application.

## References

- Feroxbuster
- SecLists (GitHub)
- PortSwigger Web Security Academy