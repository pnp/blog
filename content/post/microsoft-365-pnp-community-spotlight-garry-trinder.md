---
title: "Microsoft 365 PnP Community Spotlight: Garry Trinder"
date: 2021-05-22T04:54:00-04:00
author: "Luise Freese"
githubname: LuiseFreese
categories: ["Microsoft 365 community spotlight"]
images:
- images/blog/microsoft-365-pnp-community-spotlight-garry-trinder/garrytrinder.jpg
tags: []
type: "regular"
---

## Which community project do you maintain? 

CLI for Microsoft 365 

## How does it help people?  


CLI for Microsoft 365 is a cross platform, command line interface that helps developers and administrators manage their Microsoft 365 tenants and SharePoint Framework projects, using any operating system and any command line shell. 

## What have you been working on lately? 

I have recently been working on making the CLI more accessible to new users and new contributors to the project.  
 
We recently released our public Docker images, Docker enables us to bundle a pre-configured version of CLI for Microsoft 365 together with all its required dependencies into a publicly downloadable image, which you can then use to create an isolated environment on your local machine, called a container, where you can use the CLI for Microsoft 365 without cluttering your machine with dependencies, and all performed by executing just a single command. 
 
One of the difficulties of getting started with a new project is setting up the development environment, installing dependencies and hoping that you've followed all the instructions correctly. We know that this can be time consuming but also put off potential contributors to the project, so we've looked at ways in which we can make contributor onboarding as simple as possible, so we have provided a definition for creating an instant development environment that contains all the dependencies needed to contribute to CLI for Microsoft 365, whether that is making code changes or making an update to the documentation, we have you covered. We also automate the initial configuration steps for you when the development environment is being created, so we run npm install to install the necessary packages from npm, npm run build to build the CLI source and create a symbolic link by running npm link to ensure that when you execute m365 it uses the code in the src directory. You can use our development environment in the cloud using GitHub Codespaces or locally using Visual Studio Code Remote Development Containers. 

## What do you do at work? 

At work I am a Solutions Architect and Development Team lead for CPS, a Microsoft Gold Partner. I work primarily with Microsoft 365 and Microsoft Azure, in recent years I have been mainly focused on integration and automation. 

## Why are you a part of the M365 community? 

I believe that by sharing our own knowledge and experiences, we can improve the quality of the solutions created by the community. I have been privileged to have been part of the community for many years and I have directly benefited from others sharing their knowledge with me, it is this that drives me to contribute to the community so that others can benefit in the way that I have. 

## What was you first community contribution? 

I submitted a pull request to add a new command to CLI for Microsoft 365 which enables users to delete a Microsoft Teams channel.

## One tip for someone who’d like to start contributing 

Don't be afraid to ask questions, the Microsoft 365 community is incredibly welcoming and everyone wants to help each other, there are no stupid questions.
