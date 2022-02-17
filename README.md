# go-cloud-functions

A sample cloud function with github actions set up for deployment to GCP

## GCP setup

### create a service account

[Create a new service account](https://console.cloud.google.com/iam-admin/serviceaccounts/create) and assign it the required roles

* Cloud Functions Service Agent
* Cloud Functions Admin

## Github Setup

### Secrets

* GCP_PROJECT_ID - project id
* GCP_SA_KEY - service account json secret

## testing

### local testing

```bash
    > go run cmd/main.go
    > curl localhost:8080
    Hello World!
```

### deployed function

```bash
curl -H "Authorization: bearer $(gcloud auth print-identity-token)" https://<region>-<project_id>.cloudfunctions.net/go-cloud-function-template
 ```
