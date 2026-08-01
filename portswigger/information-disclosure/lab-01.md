# Lab 01 - Source Code Disclosure via Backup Files

## Category
Information Disclosure

## Objective

Find sensitive source code exposed through backup files.

## Skills Learned

- Information Gathering
- Reading robots.txt
- Identifying exposed backup directories
- Recognizing source code disclosure

## Steps

1. Opened the lab.
2. Checked the robots.txt file.
3. Found the `/backup` directory.
4. Opened `ProductTemplate.java`.
5. Discovered database credentials in the source code.
6. Submitted the required password to solve the lab.

## Impact

Exposed source code may reveal:

- Database credentials
- API Keys
- Internal logic
- Sensitive configuration

This information can help attackers discover additional vulnerabilities.

## Prevention

- Never expose backup directories publicly.
- Remove source code backups from production servers.
- Restrict access to sensitive files.
- Review deployment configurations.

## What I Learned

This lab taught me that even without exploiting the application,
publicly accessible source code can leak sensitive information that
may lead to more serious attacks.