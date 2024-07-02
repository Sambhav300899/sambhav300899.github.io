---
title: "Part 2: Hosting your custom MLflow server on GCP with cloud run"
date: 2024-06-26
draft: true
description: Host your own MLflow experiment tracking server on GCP 
slug: mlflow-on-gcp-2
tags:
  - mlops
  - gcp
series: ["MLflow on GCP"]
series_order: 2
---

## Motive

In part 1 of the series, we looked at how we can host our own tracking server on GCP using a VM, we did see many issues with the earlier approach though, with regards to authentication, versioning, manual resource management etc. In this article, we will look at how we can use cloud run to host our server, some of the advantages that cloud run provides is that we don't need to worry about scalability and idle resources, along with providing a cleaner way for containerisation. 

Along with this we will also try to add some form of authentication and see the changes required to push data to the MLflow server along with authentication.

## We start with the same 