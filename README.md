# Introduction

This document is intended for Signzy’s clients who wish to install Signzy’s product in their environment. This doc details an easy-to-use "Do it Yourself" CLI tool for installing the product. The environment can be on-premise or a self-hosted cloud environment.

This setup is a three-step process:

1. Download the **“signzy-self-setup-\*”** toolbox
2. Run the configurations
3. Run the installation

Follow through the below step-by-step guide for configuration and installation.

### The Sequence of configuration and installation

You should follow the below-mentioned sequence while setting up the system:

1. DB server _(MongoDB, Redis, etc)_
2. App server _(NodeJS, Python, Video KYC, and AI services)_
3. Webserver _(Nginx & Certificate setup)_

**It is important to follow this sequence as each step is a prerequisite for the next step.** As an example, MongoDB in the DB layer should be up and running for the NodeJS to properly connect and boot up.







![](.gitbook/assets/logo-wide.png)
