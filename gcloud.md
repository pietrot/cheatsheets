
## Preface
- Configurations and Accounts are separate components

## Browse list of configurations
```sh
$ gcloud config configurations list
```

## Activate a configuration
```sh
$ gcloud config configurations activate {config_name}
$ gcloud config configurations list # To confirm change
```

## Switch project
```sh
$ gcloud config set project {project_id}
$ gcloud config configurations list # To confirm change
```

## Lists credentialed accounts. Set active account
```sh
$ gcloud auth list
$ gcloud config set account {email}

OR

$ gcloud init # If you don't have an account setup

# @see https://cloud.google.com/sdk/gcloud/reference/auth/list
```

