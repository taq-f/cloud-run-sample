# cloud-run-example

## Preparation

Create a project (for example, `cloud-run-example`).

## Build

Modify `cloud-build.yml` and set the project name (`cloud-run-example`) and container name (`cloud-run-container`).

Then use gcloud tool to build.

```
gcloud builds submit --project "[your project, eg. cloud-run-example]" --config=./cloud-build.yml
```

Make sure the container open port **8080**.

You can see `cloud-run-container` in Container Registry section in GCP web UI.

## Deploy

```
gcloud beta run deploy cloud-run-example --region us-central1 --allow-unauthenticated --project "cloud-run-example" --image gcr.io/cloud-run-example/cloud-run-container
```

Url will be provided when the container is successfully deployed.
