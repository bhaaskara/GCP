# IAM
## Service accounts
List of service accounts in a project  
`gcloud iam service-accounts list --project  <bt-gbl-service-view-dp-dev>`
![](2022-11-07-18-11-02.png)

List of IAM roles assigned to the project
`gcloud projects get-iam-policy`
![](2022-11-07-18-10-09.png)


1. Authenticate with GCP
	`gcloud auth login`
	Note: Above command opens a browser and login with your GCP credentials.
2. List the projects accessible by the current user
	`gcloud projects list`
3. Set the project
	`gcloud config set project PROJECT_ID`
4. List the current project
	`gcloud config get-value project`

## List of components installed
i.e bq,gsutil

`gcloud components list`
```
Your current Google Cloud CLI version is: 410.0.0
The latest available version is: 412.0.0

+---------------------------------------------------------------------------------------------------------------+
|                                                   Components                                                  |
+------------------+------------------------------------------------------+--------------------------+----------+
|      Status      |                         Name                         |            ID            |   Size   |
+------------------+------------------------------------------------------+--------------------------+----------+
| Update Available | BigQuery Command Line Tool                           | bq                       |  1.6 MiB |
| Update Available | Cloud Storage Command Line Tool                      | 
gsutil                   | 15.5 MiB |
| Update Available | Google Cloud CLI Core Libraries                      | core                     | 25.9 MiB |
```

# Cloud storage

List all the buckets, folder and objects in a project
```
gsutil -o GSUtil:default_project_id=bt-gbl-pe-hws-dpn-dp-test du -shc
```

```
gcloud storage buckets list
gcloud storage ls
```
[gcloud storage cp ](https://cloud.google.com/sdk/gcloud/reference/storage/cp)
will be replacement for gsutil.

delete a bucket
- gcloud auth login --cred-file=$CI_PIPELINE_ID.json
- gcloud config set project bt-gbl-central-en-c-proc
- gsutil rm -r gs://europe-west2-composer-prod-c-6b33bef3-bucket-workforce
```
# Composers
`gcloud composer environments list --project <proj ID>`
Upgrade the composer
`- gcloud beta composer environments update "composer-archtctdpn-dev" --location europe-west2 --image-version composer-2.6.5-airflow-2.6.3 --project="bt-btb-archtctdpn-dp-dev-proc" --quiet`

## Delete the routes
```
 - gcloud compute routes delete composer-env-private-route composer-env-restricted-route --quiet
    # - gcloud compute routes delete composer-env-restricted-route --quiet
    - gcloud compute routers delete composer-env-router --region=europe-west2 --project=bt-gbl-lglreg-c-proc --quiet
```
# How to get the VPC ID
on console go to VPC Networks
select the VPC name
click on equalent rest

# Gcloud auth login
login using credfile
`gcloud auth login --cred-file=<file.json>`
