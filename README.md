# Docker Lab: Containerizing a Three-Tier Application
**INET 4031 - Introductions to Systems**

This lab introduces Docker and Docker Compose by having you containerize a
real, multi-service application. You will package three components: Apache,
Flask, and MariaDB. These will be packaged into separate containers and wired together so they function as a complete application.

The application code and scaffolding are provided. Your job is to complete the Dockerfiles, verify the stack runs correctly, and document your work below.

> **Directions and explanations for this lab are on the repository Wiki.**
> Refer to the Wiki pages for step-by-step instructions.

---

# Project Overview
<!-- Briefly describe what this application does in your own words.
     What problem does it solve? What does a user interact with? -->\
     
This application is a simple IT ticket dashboard that includes a description, status, and timestamp for each ticket. It allows users to view, create, and manage tickets through a web interface. The application helps users manage tickets more efficiently by storing all ticket information in one place. Users interact with a web page served by Apache, which forwards requests to Flask. MariaDB is then used to store the ticket information.
     
# Prerequisites
<!-- List what needs to be installed or configured on the VM before this lab
     will work. Include Docker, Docker Compose, and anything else required. -->

Before running this lab, the following must be installed or configured on the VM:
- Docker
- Docker Compose
- Terminal access with sudo privileges 

# Getting Started
<!-- Explain how a new teammate would bring this stack up from a fresh clone.
     Walk through every command they need to run, in order. -->

1. git clone https://github.com/alananguyen03/inet4031-testlab12.git - clone the repository
2. cd inet4031-testlab12 - navigate to the project directory
3. docker compose up --build - build and start the stack
4. docker compose ps - check container status
5. chmod +x check-lab.sh - make the script executable
6. ./check-lab.sh - run the check script

# Configuration
<!-- Explain the .env file: what it is, what variables it contains,
     and what a teammate needs to provide that is not in this repository. -->

The .env file stores enviornment variables required by the Docker containers. It contains the following variables: 

-DB_ROOT_PASSWORD: Password for the root user
-DB_NAME: Database name
-DB_USER: Database username
-DB_PASSWORD: Database password

A teammate will need to create their own .env file before running the application, providing their own values and credentials.

# Verification
<!-- Describe how to confirm the stack is running correctly.
     Reference the check script and what a passing run looks like. -->

To confirm that the stack is running correctly:
1. Check the status of the containers and ensure they are healthy: docker compose ps
2. Run the provided check script:
- chmod +x check-lab.sh
- ./check-lab.sh

A successful run of the script should show all checks passing and no failures, confirming that the stack is functioning correctly.
