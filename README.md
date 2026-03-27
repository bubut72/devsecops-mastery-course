# DevSecOps Mastery Course

A hands-on **beginner-to-advanced DevSecOps course** built around daily lessons and end-to-end projects.

This repository is organized so that **each day has its own Markdown file**, making it easy to study, track progress, and publish updates over time.

## Who this course is for
- Developers moving into DevSecOps
- DevOps engineers adding security practices
- Software engineers who want a project-based security workflow
- Teams that want a practical roadmap from secure coding to secure delivery

## What you will learn
- DevSecOps foundations
- Secure coding in Spring Boot
- OWASP-based application security
- SAST and SCA
- Docker and container hardening
- CI/CD security with GitHub Actions
- Secrets management
- API security
- DAST with OWASP ZAP
- Kubernetes security
- Monitoring and operational security
- End-to-end DevSecOps capstone delivery

## Repository structure
```text
devsecops-course-repo/
├── README.md
├── .gitignore
└── days/
    ├── day-01.md
    ├── day-02.md
    ├── ...
    └── day-84.md
```

## How to use this repository
1. Read one day at a time.
2. Create a working project folder beside this repo or inside a `/projects` folder.
3. Commit your work daily.
4. Add screenshots, notes, issues, and fixes to each day’s Markdown file.
5. Open pull requests to yourself if you want a clean review trail.

## Daily lessons
- [Day 1: Introduction to DevSecOps](days/day-01.md)
- [Day 2: CIA Triad and Security Mindset](days/day-02.md)
- [Day 3: OWASP Top 10 Overview](days/day-03.md)
- [Day 4: Secure SDLC](days/day-04.md)
- [Day 5: Threat Modeling Basics](days/day-05.md)
- [Day 6: Start the Demo App](days/day-06.md)
- [Day 7: Spring Security Basics](days/day-07.md)
- [Day 8: Input Validation](days/day-08.md)
- [Day 9: SQL Injection](days/day-09.md)
- [Day 10: Cross-Site Scripting](days/day-10.md)
- [Day 11: CSRF Protection](days/day-11.md)
- [Day 12: Password Security](days/day-12.md)
- [Day 13: Security Headers](days/day-13.md)
- [Day 14: Secure Code Review Day](days/day-14.md)
- [Day 15: What is SAST?](days/day-15.md)
- [Day 16: Install SonarQube](days/day-16.md)
- [Day 17: Connect SonarQube to the App](days/day-17.md)
- [Day 18: Fix Sonar Findings](days/day-18.md)
- [Day 19: Quality Gates](days/day-19.md)
- [Day 20: SAST in GitHub Actions](days/day-20.md)
- [Day 21: Week 3 Mini Project](days/day-21.md)
- [Day 22: What is SCA?](days/day-22.md)
- [Day 23: Install Dependency Scanner](days/day-23.md)
- [Day 24: Fix Vulnerable Dependencies](days/day-24.md)
- [Day 25: License Risk Awareness](days/day-25.md)
- [Day 26: SCA in CI](days/day-26.md)
- [Day 27: Combine SAST + SCA](days/day-27.md)
- [Day 28: Week 4 Mini Project](days/day-28.md)
- [Day 29: Docker Fundamentals for DevSecOps](days/day-29.md)
- [Day 30: Write a Dockerfile](days/day-30.md)
- [Day 31: Docker Security Best Practices](days/day-31.md)
- [Day 32: Multi-stage Builds](days/day-32.md)
- [Day 33: Run as Non-root](days/day-33.md)
- [Day 34: Image Scanning with Trivy](days/day-34.md)
- [Day 35: Week 5 Mini Project](days/day-35.md)
- [Day 36: CI/CD Fundamentals](days/day-36.md)
- [Day 37: Create a GitHub Actions Workflow](days/day-37.md)
- [Day 38: Add Unit Tests to CI](days/day-38.md)
- [Day 39: Add SAST to CI](days/day-39.md)
- [Day 40: Add SCA to CI](days/day-40.md)
- [Day 41: Add Docker Build + Scan](days/day-41.md)
- [Day 42: Week 6 Mini Project](days/day-42.md)
- [Day 43: Secrets Management Basics](days/day-43.md)
- [Day 44: Secrets in GitHub Actions](days/day-44.md)
- [Day 45: Vault Fundamentals](days/day-45.md)
- [Day 46: Store and Retrieve Secrets](days/day-46.md)
- [Day 47: Use Vault in the Pipeline](days/day-47.md)
- [Day 48: Rotate Secrets](days/day-48.md)
- [Day 49: Week 7 Mini Project](days/day-49.md)
- [Day 50: API Security Basics](days/day-50.md)
- [Day 51: AuthN vs AuthZ](days/day-51.md)
- [Day 52: JWT Fundamentals](days/day-52.md)
- [Day 53: OAuth2 Concepts](days/day-53.md)
- [Day 54: Rate Limiting](days/day-54.md)
- [Day 55: API Gateway Security](days/day-55.md)
- [Day 56: Week 8 Mini Project](days/day-56.md)
- [Day 57: What is DAST?](days/day-57.md)
- [Day 58: Install OWASP ZAP](days/day-58.md)
- [Day 59: Scan the Application](days/day-59.md)
- [Day 60: Analyze ZAP Findings](days/day-60.md)
- [Day 61: Fix Runtime Issues](days/day-61.md)
- [Day 62: Automate DAST in CI](days/day-62.md)
- [Day 63: Week 9 Mini Project](days/day-63.md)
- [Day 64: Kubernetes Basics](days/day-64.md)
- [Day 65: Deploy the App to Kubernetes](days/day-65.md)
- [Day 66: RBAC](days/day-66.md)
- [Day 67: Network Policies](days/day-67.md)
- [Day 68: Pod Security](days/day-68.md)
- [Day 69: Runtime Security with Falco](days/day-69.md)
- [Day 70: Week 10 Mini Project](days/day-70.md)
- [Day 71: Monitoring Basics](days/day-71.md)
- [Day 72: Prometheus Setup](days/day-72.md)
- [Day 73: Grafana Dashboards](days/day-73.md)
- [Day 74: Alerting](days/day-74.md)
- [Day 75: Security Monitoring](days/day-75.md)
- [Day 76: Week 11 Mini Project](days/day-76.md)
- [Day 77: Capstone Planning](days/day-77.md)
- [Day 78: Capstone Day 1: Architecture Setup](days/day-78.md)
- [Day 79: Capstone Day 2: App Security](days/day-79.md)
- [Day 80: Capstone Day 3: CI Security](days/day-80.md)
- [Day 81: Capstone Day 4: Container + DAST](days/day-81.md)
- [Day 82: Capstone Day 5: Kubernetes Security](days/day-82.md)
- [Day 83: Capstone Day 6: Monitoring + Evidence](days/day-83.md)
- [Day 84: Capstone Day 7: Final Review and Publish](days/day-84.md)
