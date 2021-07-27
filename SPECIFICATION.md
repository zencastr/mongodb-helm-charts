# MongoDB Helm Chart Specification

:construction:
__DRAFT__

This document defines the standard structure of official 
MongoDB Helm charts along with requirements and usage patterns.

The MongoDB Helm charts are designed to provide you with multiple 
optimal pathways for using and/or running MongoDB within your Kubernetes
environments. This includes support for cloud-based MongoDB Atlas clusters, 
and locally running Community and Enterprise MongoDB clusters. 


The Official MongoDB catalog of charts is published to:

```
https://github.com/mongodb/helm-charts
```
## Using Charts

MongoDB charts have 2 types of users:

1. Administrators - installing and configuring Kubernetes Operator or Ops Manager
2. Database Service Consumers - creating, connecting, and using MongoDB database clusters

Each chart shall provide a similar experience for each type of user.

## Chart Structure


## Requirements

1. Each chart should default the name to {{ .Release.Name }}

1. Charts should always set namespace to {{ .Release.Namespace }}

1. Parameters values.yaml should be documented and proper defaults set
    1. Values files should have JSON schemas

1. No chart uses Helm dependencies, except for a chart that needs crds
    1. Each chart that needs CRDS should have a “*-crd” chart, with is the only dependency

1. Charts should have a consistent and well defined Versioning strategy

1. Charts should support latest releases for each operator, and follow similar support timeline

1. Each charts should allow ability to add existing db clusters into k8s, or add existing clusters or projects in Atlas as CR instance; (Create or Read pattern)

1. Each chart that deploys a db should enable authentication by default
MONGODB user/password, we should enable the simplest authentication by default and support other modes, such as x509, or IAM Roles through additional charts and extras

1. Each chart that provisions a db-user should

1. Generate a random password or require the user to create one

1. Provide a standard ConnectionStrings object in a Kubernetes Secret in a common format

1. Applications should be able to switch between clusters/dbusers created by different charts without any changes. Applications should be freely portable across all applicable charts.

1. Each chart should have a well defined process for maintenance from its source operator code repository.
Clusters, projects and other resources managed by a chart should be marked as being managed through Kubernetes and Helm

1. Add Labels to all managed resources, Projects, Clusters, DBUsers

1. Each Chart should document which value set for User-Agent

