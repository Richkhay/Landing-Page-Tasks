# Web Based Project: Simple Landing Page on AWS EC2

## Table of Contents

1. [Project Overview](#project-overview)
2. [Introduction](#introduction)
3. [Server Provisioning](#server-provisioning)
4. [Installing the Web Server](#installing-the-web-server)
5. [Deploying the HTML Page](#deploying-the-html-page)
6. [Configuring Networking](#configuring-networking)
7. [How to Access the Landing Page](#how-to-access-the-landing-page)
8. [Technologies Used](#technologies-used)
9. [Screenshots](#screenshots)

---

## Project Overview

This project outlines the step-by-step process of setting up and deploying a simple landing page on an AWS EC2 instance using an Ubuntu server and Apache2 web server. The landing page introduces myself, provides a brief bio, and includes the project title. 

The goal is to demonstrate how to provision a cloud-based server, install the Apache web server, and host a static HTML page on an Ubuntu-based EC2 instance.

---

## Introduction

*Purpose of the Document:*  
This document provides detailed instructions on how to provision a virtual machine (VM) on AWS EC2, install Apache2 web server, deploy a static HTML landing page, and configure networking for public access.

---

## Server Provisioning

1. *Log in to AWS*  
   Sign in to your AWS account and navigate to the EC2 Dashboard.

2. *Launch an EC2 Instance*  
   - Select Ubuntu as the AMI (Amazon Machine Image).
   - Choose the t2.micro instance type (eligible for the free tier).
   - Create a new key pair for SSH access.
   - Set up a Security Group to allow inbound traffic on port 80 (HTTP).

3. *Connect to the EC2 Instance*  
   Once the instance is running, connect to it via SSH:
   bash
   ssh -i "Linuxserver.pem" ec2-user@ec2-13-247-149-119.af-south-1.compute.amazonaws.com
   

---

## Installing the Web Server

1. Update the package list and install Apache2:
   bash
   sudo apt update
   sudo apt install apache2 -y
   

2. Start Apache2:
   bash
   sudo systemctl start apache2
   

3. Enable Apache2 to start on boot:
   bash
   sudo systemctl enable apache2
   

4. Check Apache2 status:
   bash
   sudo systemctl status apache2
   

5. Test the setup:  
   Visit the IP address of your EC2 instance in a web browser:
   
   http://13.247.149.119/
   

---

## Deploying the HTML Page

1. Edit the default HTML file:
   bash
   sudo vi /var/www/html/index.html
   

2. Replace the content of index.html with your custom HTML code (landing page content).

3. Save the changes and exit the text editor.

---

## Configuring Networking

1. Update Security Group for the EC2 instance:
   - *Inbound Rules:*
     - HTTP (port 80): Allow traffic from all sources (0.0.0.0/0).
     - HTTPS (port 443): Allow traffic from all sources (0.0.0.0/0).
   - *Outbound Rules:*
     - Allow all traffic (all protocols, all ports) to destination 0.0.0.0/0.

2. Verify accessibility:  
   Ensure that your security group settings allow public access to the instance and the web server.

---

## How to Access the Landing Page

Once the web server is running and the HTML page is deployed, you can view the landing page by visiting:


http://13.247.149.119/


---

## Technologies Used

- *HTML*: For creating the structure and content of the landing page.
- *CSS*: For styling the layout and design of the landing page.
- *AWS EC2*: To host the landing page in the cloud.
- *Apache2*: As the web server to serve the landing page.

---

## Screenshots

[Screensot of Landing Page](Image/Landing-page-picture.png)

