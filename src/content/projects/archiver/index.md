---
title: "Catalyst Archiver"
summary: "Automated blockchain archiving"
date: "July 2022"
draft: false
tags:
- Go
- Kubernetes
- Terraform
---

The Catalyst Archiver is a kubernetes operator that is responsible for archiving the underlying blockchain powering the Project
Catalyst infrastructure.
I designed the operator in response to a desire to bring transparency to the Project Catalyst community for our private blockchain.

The operator provides a number of custom resources for scheduling the creation of snapshots of the underlying blockchain at routine
intervals.
The operator then oversees the entire lifecycle of a snapshot: archiving it, uploading it to IPFS, and creating a tamper-proof
fingerprint of the snapshot that could be used to prove that it was crpytographically valid.
I also developed a Go-based API that end-users could consume for searching, downloading, and validating these snapshots.