# Day 1: Introduction to DevSecOps

## Day 1 outcome

By the end of today, you should be able to:

* explain DevOps and DevSecOps in simple language
* describe why security cannot be added only at the end
* understand the idea of **shift left**
* explain where security fits in the software lifecycle
* set up the basic tooling you will use in this course
* create the first starter project for the course

---

# 1. What DevOps is

Let’s start from the beginning.

## Traditional software delivery

In many organizations, software work used to happen like this:

1. Developers wrote code
2. QA tested it later
3. Operations deployed it later
4. Security reviewed it near the end

This sounds organized, but it causes problems.

The biggest problem is that each group works like a separate island.

* Developers focus on features
* QA focuses on bugs
* Operations focuses on stability
* Security focuses on risk

Because these groups work at different times, issues are often found late.

For example:

* a developer writes insecure code in week 1
* QA tests functionality in week 3
* security finds a vulnerability in week 5
* ops struggles to deploy the fix in week 6

That means the feedback loop is slow, expensive, and frustrating.

---

## DevOps idea

DevOps tries to solve this by bringing together:

* **Dev** = Development
* **Ops** = Operations

DevOps is not only a toolset. It is mainly a way of working.

The goal is to make software delivery:

* faster
* more reliable
* more repeatable
* more collaborative

In DevOps, teams aim to automate:

* building
* testing
* packaging
* deployment
* monitoring

So instead of manual handoffs, you get a pipeline.

### Example

A developer pushes code to GitHub.

Then automatically:

* the app builds
* tests run
* an artifact is created
* a container image is built
* deployment happens to an environment

This is much better than emailing ZIP files or manually copying builds to servers.

---

# 2. What DevSecOps is

Now let’s add the missing piece.

## DevSecOps meaning

DevSecOps = **Development + Security + Operations**

It means security becomes part of the entire delivery process, not a separate late-stage checkpoint.

Security is not something you “bolt on” at the end.

Security becomes:

* part of design
* part of coding
* part of dependencies
* part of pipelines
* part of infrastructure
* part of deployment
* part of monitoring

So DevSecOps says:

> Build fast, but also build safely.

---

## The core idea

Instead of this:

**build first, secure later**

You do this:

**build securely from the beginning**

That is the heart of DevSecOps.

---

# 3. Why traditional security fails

Let’s make this very practical.

Imagine your team builds a payment service.

At the end of the project, security finds:

* weak authentication
* vulnerable dependency
* exposed admin endpoint
* secrets committed into Git
* insecure Docker image

Now what happens?

* developers must revisit old code
* deadlines slip
* trust drops
* production risk increases
* fixing cost becomes very high

This is why late security is painful.

There is a famous general principle in software engineering:

> The later you find a problem, the more expensive it is to fix.

That is true for bugs, and it is especially true for security issues.

---

# 4. Shift Left

This is one of the most important ideas in DevSecOps.

## What shift left means

Think of the software lifecycle as a timeline from left to right:

* planning
* design
* coding
* testing
* deployment
* production

Traditionally, security used to sit far to the right, near release or production.

**Shift left** means moving security activities earlier, closer to planning, design, and coding.

So instead of waiting until the end, we ask security questions early.

---

## Example of shift left

### Old way

A developer writes an API, deploys it, and later a security team says:

* no input validation
* weak auth
* no rate limits
* outdated library

### Shift-left way

Before coding even starts, the team asks:

* what data is sensitive?
* who can call this API?
* what are the abuse cases?
* how will we validate input?
* how will we manage secrets?
* how do we prevent dependency risk?

This saves time and reduces risk.

---

## Important clarification

Shift left does **not** mean only early security.

It means **early security plus continuous security**.

You still need security in production too.

So DevSecOps is not just shift left. It is also:

* shift left
* automate
* monitor continuously
* respond quickly

---

# 5. DevOps vs DevSecOps

Here is the practical difference.

## DevOps focus

DevOps focuses on:

* speed
* automation
* reliable delivery
* collaboration between dev and ops

## DevSecOps focus

DevSecOps focuses on all of the above, plus:

* secure design
* secure coding
* automated security checks
* secrets protection
* supply chain security
* runtime monitoring
* compliance awareness

So DevSecOps is not anti-speed.

It says:

> Speed without security is dangerous.
> Security without automation is too slow.

The goal is secure speed.

---

# 6. Real-world example: Spring Boot microservice

Let’s use a simple example close to your background.

Suppose you are building a Spring Boot microservice called `order-service`.

A normal DevOps pipeline might do:

* compile code
* run unit tests
* build JAR
* build Docker image
* deploy to Kubernetes

A DevSecOps pipeline would also do:

* run static code analysis
* scan dependencies for CVEs
* check secrets are not hardcoded
* scan container image
* verify Kubernetes manifests
* enforce policy checks
* run dynamic security tests
* monitor runtime events

That is the mindset change.

---

# 7. Security is everybody’s responsibility

This is another core principle.

In older models, teams often thought:

* developers write code
* security team handles security

That does not scale.

In DevSecOps:

* developers write more secure code
* architects design safer systems
* ops configures secure infrastructure
* security engineers create guardrails, automation, and standards
* everyone shares responsibility

This does **not** mean every developer becomes a full-time security expert.

It means security becomes part of normal engineering work.

---

# 8. The software development lifecycle in DevSecOps

Now let’s walk through the lifecycle.

## 8.1 Planning

At this stage, teams decide what to build.

Security questions here include:

* what data will the app process?
* does it handle PII, credentials, payments, tokens?
* what regulations apply?
* what are the business risks?
* what misuse cases exist?

### Example

If your app stores customer passwords, you must plan for:

* password hashing
* access control
* audit logging
* secrets management

If you ignore these during planning, you will pay later.

---

## 8.2 Design

This is where architecture decisions happen.

Security questions here include:

* where does authentication happen?
* how do services trust each other?
* how are secrets stored?
* what data should be encrypted?
* what attack paths exist?
* how do we isolate services?

### Example

Suppose you decide:

* frontend calls API gateway
* gateway routes to microservices
* each microservice validates JWT
* database credentials come from secrets manager
* internal services communicate over TLS

That is security-aware design.

---

## 8.3 Coding

Now developers implement the system.

Security here includes:

* secure coding practices
* input validation
* safe error handling
* secure logging
* avoiding hardcoded secrets
* parameterized queries
* dependency hygiene

### Bad example

```java
String sql = "SELECT * FROM users WHERE username = '" + username + "'";
```

This can cause SQL injection.

### Better example

Use parameterized queries or Spring Data JPA.

Security starts in code.

---

## 8.4 Build

When code is built, you can automatically check it.

Security checks here include:

* static application security testing
* secret scanning
* dependency scanning
* license checks
* artifact integrity

This is where automation begins to help a lot.

---

## 8.5 Test

Testing is not only functional testing.

Security testing includes:

* authentication testing
* authorization testing
* input validation testing
* API abuse testing
* DAST
* negative testing

### Example

Test not only “can valid users access endpoint?”

Also test:

* can invalid users access it?
* can users access other users’ data?
* does malformed input break the system?

---

## 8.6 Package

If you package into Docker images or artifacts, security matters here too.

Questions include:

* is the base image minimal?
* are vulnerable packages included?
* are we running as root?
* are unnecessary tools installed?
* is the image scanned?

---

## 8.7 Deploy

Deployment should include security controls.

Examples:

* environment secrets injected securely
* least privilege IAM roles
* Kubernetes RBAC
* network policies
* admission controls
* policy checks

---

## 8.8 Operate and monitor

Production is not the end.

You still need:

* logging
* metrics
* tracing
* audit events
* runtime security alerts
* anomaly detection
* incident response

DevSecOps continues after deployment.

---

# 9. CI/CD and where security fits

You will hear this constantly, so let’s make it clear.

## CI = Continuous Integration

Developers frequently merge code into a shared repo.

Typical CI steps:

* checkout code
* build
* unit test
* lint
* package

## CD = Continuous Delivery or Continuous Deployment

The app is prepared for release or automatically released.

Typical CD steps:

* deploy to test
* integration tests
* deploy to staging
* approval or auto-release
* deploy to production

## DevSecOps in CI/CD

Security becomes part of this pipeline.

Example pipeline:

1. developer pushes code
2. app builds
3. tests run
4. SAST runs
5. dependency scan runs
6. secrets scan runs
7. Docker image builds
8. image scan runs
9. deploy to test
10. DAST runs
11. deploy if policy passes

This is the automation backbone of DevSecOps.

---

# 10. Key DevSecOps practices you will learn in this course

Today you only need awareness, not mastery.

## Secure coding

Writing code that avoids common vulnerabilities.

## SAST

Analyzing source code for security issues without running the app.

## SCA

Scanning third-party libraries and dependencies for known vulnerabilities.

## Secrets management

Handling passwords, tokens, keys, and credentials safely.

## Container security

Building secure Docker images and scanning them.

## IaC security

Checking Terraform, Kubernetes YAML, or Helm charts for risky configuration.

## DAST

Testing a running application from the outside.

## Runtime security

Watching what happens in production and detecting suspicious behavior.

## Policy as code

Encoding rules so insecure changes are automatically blocked.

---

# 11. Important DevSecOps mindset changes

Let’s slow down here because this matters a lot.

## Mindset 1: Security is not a gate at the end

Security should be built in continuously.

## Mindset 2: Automation is essential

Manual review alone does not scale.

## Mindset 3: Secure defaults are powerful

Make the safe path the easy path.

## Mindset 4: Developers need feedback early

If security feedback comes days later, it is often ignored or delayed.

## Mindset 5: Perfect security is impossible

The goal is risk reduction, not magical zero risk.

## Mindset 6: Balance matters

A DevSecOps program that blocks everything becomes useless.
A pipeline with no controls becomes dangerous.
You want practical, automated guardrails.

---

# 12. A concrete end-to-end scenario

Imagine this project:

* Spring Boot backend
* PostgreSQL database
* Docker container
* GitHub Actions pipeline
* Kubernetes deployment

Without DevSecOps, common mistakes might include:

* password in `application.properties`
* outdated dependency with known CVE
* container running as root
* open admin endpoint
* no auth on internal API
* permissive Kubernetes role
* no image scanning
* no monitoring

With DevSecOps, the process becomes:

* secrets moved to secure storage
* dependency scanning catches CVEs
* code scan flags risky patterns
* Docker image is hardened
* Kubernetes config is checked
* production is monitored
* risky builds are blocked early

That is what we are training for.

---

# 13. Day 1 tool setup

Now let’s do the hands-on part.

For Day 1, we will keep setup simple and practical.

## What to install

You should have:

* Git
* Java 21 or 17
* Maven
* Docker
* VS Code
* GitHub account

Since you are on Ubuntu, here are the commands.

## Update packages

```bash
sudo apt update
```

## Install Git

```bash
sudo apt install git -y
```

## Verify Git

```bash
git --version
```

## Install Java

If you want Java 21:

```bash
sudo apt install openjdk-21-jdk -y
```

If Java 21 is unavailable in your Ubuntu repo, install Java 17:

```bash
sudo apt install openjdk-17-jdk -y
```

## Verify Java

```bash
java -version
javac -version
```

## Install Maven

```bash
sudo apt install maven -y
```

## Verify Maven

```bash
mvn -version
```

## Install Docker

```bash
sudo apt install docker.io -y
```

## Start Docker

```bash
sudo systemctl enable docker
sudo systemctl start docker
```

## Verify Docker

```bash
docker --version
```

If you get permission denied when running Docker as a normal user:

```bash
sudo usermod -aG docker $USER
```

Then log out and log back in, or reboot.

After that test:

```bash
docker run hello-world
```

---

# 14. Create the Day 1 starter project

Today’s goal is not security tooling yet.
Today’s goal is to create the base application we will secure over the coming days.

We’ll create a simple Spring Boot app.

## Project idea

A tiny service called `secure-shop`.

It will start with:

* one controller
* one endpoint
* simple JSON response

Later we will make it secure.

---

## Option A: Create with Spring Initializr in browser

Use:

* Project: Maven
* Language: Java
* Spring Boot: latest stable
* Group: `com.devsecops`
* Artifact: `secure-shop`
* Packaging: Jar
* Java: 17 or 21

Dependencies:

* Spring Web
* Spring Boot DevTools
* Spring Security
* Validation

Download and unzip.

---

## Option B: Create manually using curl

If you want, I can give you that later. For today, browser-based creation is easiest.

---

# 15. Recommended folder structure

After unzipping, open the project in VS Code. You should see something like:

```text
secure-shop/
  pom.xml
  src/
    main/
      java/
        com/devsecops/secureshop/
          SecureShopApplication.java
      resources/
        application.properties
    test/
```

---

# 16. First run

Open terminal in the project folder and run:

```bash
mvn spring-boot:run
```

If successful, you should see Spring Boot start.

Stop it with:

```bash
Ctrl + C
```

---

# 17. Add your first controller

Create this file:

`src/main/java/com/devsecops/secureshop/HelloController.java`

```java
package com.devsecops.secureshop;

import org.springframework.web.bind.annotation.GetMapping;
import org.springframework.web.bind.annotation.RestController;

import java.util.Map;

@RestController
public class HelloController {

    @GetMapping("/hello")
    public Map<String, String> hello() {
        return Map.of(
                "message", "Welcome to DevSecOps Day 1",
                "status", "running"
        );
    }
}
```

Now run again:

```bash
mvn spring-boot:run
```

Open browser:

```text
http://localhost:8080/hello
```

Because Spring Security is included, you may see a login prompt or secured behavior depending on your setup. That is okay. Tomorrow and later lessons will explain this deeply.

For today, the point is:

* the app runs
* the project exists
* we begin with a realistic base

---

# 18. Create your Day 1 notes file

Inside your course repo, edit `days/day-01.md`.

You can put this structure in it.

```md
# Day 1 - DevSecOps Foundations

## What I learned
- DevOps combines development and operations for faster, more reliable delivery.
- DevSecOps adds security into the entire lifecycle.
- Shift left means moving security earlier into planning, design, and coding.
- Security is not only a final review step.
- Automation is essential for scalable security.

## Tools installed
- Git
- Java
- Maven
- Docker

## Hands-on completed
- Created Spring Boot starter project
- Added first REST endpoint
- Ran the application locally

## Reflection
Security must be part of how software is designed and delivered, not just tested at the end.
```

---

# 19. Day 1 lab

Here is your practical exercise for today.

## Lab 1: Environment verification

Run these commands and confirm they all work:

```bash
git --version
java -version
mvn -version
docker --version
```

## Lab 2: Create and run the Spring Boot project

* create the project
* open it in VS Code
* run `mvn spring-boot:run`

## Lab 3: Add `/hello` endpoint

* create `HelloController.java`
* run the app
* test `http://localhost:8080/hello`

## Lab 4: Commit to GitHub

In your project folder:

```bash
git add .
git commit -m "complete day 01 starter project"
git push
```

---

# 20. Common Day 1 mistakes

## Mistake 1: Treating DevSecOps as only tools

DevSecOps is mainly a process and culture change, supported by tools.

## Mistake 2: Thinking security belongs only to the security team

It is a shared responsibility.

## Mistake 3: Believing shift left means security ends early

It starts early and continues throughout the lifecycle.

## Mistake 4: Installing tools without understanding why

Every tool should map to a security need.

## Mistake 5: Jumping into advanced scanners before building a base app

You need a real application target first.

---

# 21. Interview-style questions for Day 1

Try answering these yourself.

## Question 1

What is the difference between DevOps and DevSecOps?

**Answer:**
DevOps focuses on collaboration, automation, and faster software delivery between development and operations. DevSecOps extends this by integrating security into every phase of the lifecycle, including coding, build, test, deployment, and monitoring.

## Question 2

What does shift left mean?

**Answer:**
Shift left means moving security activities earlier in the lifecycle, especially into planning, design, and coding, so issues are identified sooner and fixed at lower cost.

## Question 3

Why is late security expensive?

**Answer:**
Because issues found late often require redesign, recoding, retesting, redeployment, and coordination across teams, which increases cost and delays release.

## Question 4

Is DevSecOps only about automated scanners?

**Answer:**
No. It includes culture, secure design, shared responsibility, secure coding, automated testing, secrets management, deployment controls, and runtime monitoring.

---

# 22. Simple analogy

Think of building a house.

## Traditional late security

You build the whole house and only at the end ask:

* should there have been locks?
* are there fire exits?
* is the wiring safe?

That is expensive and messy.

## DevSecOps

You ask those questions while designing the house.

That is smarter, cheaper, and safer.

---

# 23. What you should remember most from Day 1

If you remember only five things, remember these:

1. **DevSecOps means security is part of delivery, not separate from it.**
2. **Shift left means think about security early.**
3. **Security should be automated wherever possible.**
4. **Security is a shared responsibility.**
5. **You need a real application base before adding security tooling.**

---

# 24. Homework

Complete these today:

* install Git, Java, Maven, Docker
* verify each installation
* create the Spring Boot starter project
* add the `/hello` endpoint
* run the app locally
* update `days/day-01.md`
* commit and push to GitHub

Use this commit message:

```bash
git add .
git commit -m "complete day 01 devsecops foundations"
git push
```

---

Tomorrow, Day 2 should cover **CIA triad, security goals, and risk thinking**, and then connect those concepts to real software systems.