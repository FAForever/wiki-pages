---
title: DevOps Roadmap
description: 
published: true
date: 2025-02-01T20:15:12.755Z
tags: 
editor: markdown
dateCreated: 2025-02-01T20:15:12.755Z
---

# DevOps Roadmap 2025 and beyond
Last update: 01. Feb 2025

* Feature: Map Vetos
  * allow users voting for maps they do not ant to play on
  * affects: Client, Lobby Server, API, commons lib
* Operations: Cleanup Kubernetes transition fallout
  * Logging can pollute the disk
  * Fix SMB storage integration for replays
* Feature: OAuth device flow
  * Removes weird login redirect page for desktop apps
  * affects: FAF Client, Moderator client, Ory Hydra
* Feature: Improve account security
  * classified
* Architecture: Transition account self service from website to user service
  * the website is in a really bad state and with no developers
  * moving the account service should allo for better UX e.g. on Steam Link
  * affects: website, user service, API
* Architecture: Decouple lobby server from ice adapter candidate exchange
  * allow game sessions to run even if lobby server is restarted