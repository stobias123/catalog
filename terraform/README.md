# Terraform

Simple terraform task

## Install the Task

```
kubectl apply -f https://raw.githubusercontent.com/stobias123/catalog/master/s2i/s2i.yaml
```

## Inputs

### Parameters

* **WORKSPACE**: Your terraform workspace

### Resources

* **source**: A `git`-type `PipelineResource` specifying the location of the
  source to build.

## Outputs

### Resources

N/A

## ServiceAccount

If you want to access any secrets from your tf plan. Use the service account.

## Usage

This TaskRun runs the Task to fetch a Git repo, and run terraform init and plan.

```
apiVersion: tekton.dev/v1alpha1
kind: TaskRun
metadata:
  generatedname: testmodule-tf-plan-
spec:
  serviceAccount: "pipeline"
  taskRef:
    name: terraform
  inputs:
    resources:
    - name: source
      resourceRef:
        name: terraform-module
```