# Initialization

## Bootstrap a new GCP project

1. Create your GCP project (through https://console.cloud.google.com)

2. Login with a user that has full owner access to the project

```sh
$ gcloud auth login
```

3. Set your project in your gcloud cli config (important for the next commands)

```sh
$ gcloud config set project {project_id}
```

4. Ensure your GCP project has a working billing account `https://console.cloud.google.com/billing/linkedaccount`

5. Enable required services
   _Note_ This command may take a few minutes

```sh
$ gcloud services enable iamcredentials.googleapis.com --project="{project_id}"
$ gcloud services enable storage.googleapis.com --project="{project_id}"
$ gcloud services enable cloudresourcemanager.googleapis.com --project="{project_id}"
```

6. Create a `terraform` state bucket in Google Storage (`{project_id}-terraform-state`)

```sh
$ gsutil mb -l us-east1 gs://{project_id}-terraform-state
```

7. Create `terraform` service account in the new project

```sh
$ gcloud iam service-accounts create terraform \
    --description="Terraform Service Account" \
    --display-name="Terraform Service Account"
```

8. Grant `terraform` service account roles

```sh
$ gcloud projects add-iam-policy-binding {project_id} \
--member='serviceAccount:terraform@{project_id}.iam.gserviceaccount.com' \
--role='roles/owner'

$ gcloud projects add-iam-policy-binding {project_id} \
--member='serviceAccount:terraform@{project_id}.iam.gserviceaccount.com' \
--role='roles/storage.admin'
```

## Import `terraform` state bucket
```sh
$ terraform import google_storage_bucket.gs-{project_id}-terraform-state {project_id}/{project_id}-terraform-state
```

## Upgrade provider
```sh
$ terraform init -upgrade
```
—https://developer.hashicorp.com/terraform/tutorials/configuration-language/provider-versioning
