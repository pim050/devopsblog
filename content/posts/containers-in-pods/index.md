---
title: "Containers in pods"
date: 2026-11-08T14:36:30+01:00
draft: true
categories: ["devops-blog"]
tags: ["kubernetes","pods","container","storage"]
---

I learned that inside a kubernetes pod you can run more than one container.
When you define them in the array you can assign a storage volume, either ephemeral in the pod. Or, persistently on a volume somewhere else.

Entering one of the containers, you can find the folders you declared in the deployment.yaml. And so, containers inside this pod, can have access to a shared folder. A file created in Container A, can be seen in Container B.

Deleting the pod and letting it get recreated gave me an empty folder. The volume was ephemeral: it cat survive a container restart, but not pod deletion.


