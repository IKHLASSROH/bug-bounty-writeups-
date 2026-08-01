# Lab 03 - Source Code Disclosure via Exposed .git Directory

## Category

Information Disclosure

## Difficulty

Apprentice

---

## Objective

Gain access to sensitive information by exploiting an exposed `.git` directory.

---

## Tools Used

- Browser
- Feroxbuster
- SecLists (GitHub Wordlists)
- Git
- Wget
- PortSwigger Web Security Academy

---

## Methodology

1. Explored the target application manually.
2. Used **Feroxbuster** with the **SecLists** `common.txt` wordlist to enumerate hidden files and directories.
3. Discovered an exposed `.git` directory.
4. Downloaded the exposed Git repository using `wget`.
5. Opened the repository locally with **Git**.
6. Reviewed the commit history using `git log`.
7. Identified a commit indicating that the administrator password had been removed from a configuration file.
8. Retrieved the previous version of the configuration file using Git.
9. Used the recovered credentials to access the administrator panel.
10. Deleted the target user and successfully solved the lab.

---

## Vulnerability

The web application exposed its `.git` directory, allowing anyone to download the Git repository.

An exposed Git repository may reveal:

- Source code
- Configuration files
- Credentials
- API keys
- Commit history
- Previously deleted secrets

---

## Security Impact

This vulnerability can allow attackers to:

- Recover deleted credentials
- Analyze source code
- Discover hidden endpoints
- Understand the application's internal structure
- Find additional vulnerabilities

---

## Mitigation

- Never expose the `.git` directory in production.
- Block access to hidden directories.
- Remove Git metadata before deployment.
- Review repositories for sensitive information before publishing.

---

## Commands Used

```bash
git log
git show
wget -r <target-url>/.git/
```

---

## What I Learned

This lab taught me that exposing a Git repository is a serious Information Disclosure vulnerability. Even if sensitive information has been deleted from the latest version of the application, Git history may still contain credentials or other secrets that attackers can recover.