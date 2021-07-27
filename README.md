# MongoDB Helm Charts


This repository contains HELM charts for different MongoDB products.
The catalog of charts is currently :building_construction: *UNDER ACTIVE DEVELOPMENT*. 

Anticipating _official Beta_ Fall 2021 at which point this Github repo will be the offical MongoDB 
Helm Chart source.

## Getting Started

Add `https://mongodb.github.io/helm-charts` to your Argo, or other your other Helm manager
or go use the usual way:

```bash
helm repo add mongodb https://mongodb.github.io/helm-charts
helm dependency update
```

The simplest way to get started is to use the MongoDB Atlas operator, this 
lightwight option connects database clusters running in the MongoDB Cloud to 
your Kubernetes clusters. If you need, [setup](#Setting-up-a-MongoDB-Cloud-account) 
you MongoDB Cloud account.

```bash
helm install atlas-operator mongodb/atlas-operator \
 --set globalConnectionSecret.publicApiKey=${ATLAS_PUBLIC_KEY} \
 --set globalConnectionSecret.privateApiKey=${ATLAS_PRIVATE_KEY} \
 --set globalConnectionSecret.orgId=${ATLAS_ORG_ID} \
```


## The Charts

| Charts                  | Description                                        |
|-------------------------|----------------------------------------------------|
| atlas-operator          | MongoDB Atlas Helm Chart. Install Operator Chart   |
| atlas-operator-crds     | MongoDB Atlas Collection of CRD's                  |
|-------------------------|----------------------------------------------------|
| community-operator      | The MongoDB Community Kubernetes operator.         |
| community-database      | Community MongoDB standalone and replicasets.      |
|-------------------------|----------------------------------------------------|
| ent-operator            | MongoDB Enterprise Kubernetes operator.            |
| ent-operator-database   | Deploy MongoDB Enterprise DataBase.                |
| ent-operator-opsmanager | Deploy MongoDB Enterprise OpsManager.              |
|-------------------------|----------------------------------------------------|
| fastapi-sample-app      | Example app to test your MongoDB databases.        |

## Getting Started - Community Operator

	:construction:

## Getting Started - Enterprise Operator

	:construction:

## FastApi Sample App

	:construction:

TODO - instructions on using sample fastapi all. Needs work same on all operators.

    charts/fastapi-sample-app/values-enterprise.yaml
    charts/fastapi-sample-app/values.yaml

## Setting up a MongoDB Cloud account

In order to use the Atlas Operator you need to:

* Sign up for a [MongoDB Atlas account](https://www.mongodb.com/cloud/atlas/register)
* Skip the cluster deployment options
* Go to Billing and add a credit card to your account
* Create an organization-level [MongoDB Atlas Programmatic API Key](https://docs.atlas.mongodb.com/configure-api-access#programmatic-api-keys) with an IP Access List entry. The key needs `Organization Project Creator` permissions.









