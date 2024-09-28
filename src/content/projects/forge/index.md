---
title: "Catalyst Forge"
summary: "The developer platform powering Project Catalyst"
date: "September 2024"
draft: false
tags:
- Go
- CUE
- GitHub Actions
- Earthly
repoUrl: https://github.com/input-output-hk/catalyst-forge
---

Catalyst Forge is a custom developer platform that I was responsible for architecting and implementing.
The platform brings super powers to "mono-repos" by breaking them up into discrete projects, each with a dedicated configuration
file that contains all necessary information for building, testing, and deploying the project.
It includes a full CI system that uses a unique discovery system for automatically discovering and integrating projects into a
single pipeline.
It also provides several quality of life improvements including an intelligent tag management system, automatic releases, simplified
cross-platform builds, and more.
