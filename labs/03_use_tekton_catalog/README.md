# Use Tekton CD Catalog

This folder holds the files for the lab: _Use Tekton CD Catalog_ which is part of the **IBM-CD0215EN-Skills Network Introduction to CI/CD** course.

## The command to install the git-clone task from Tekton Hub:
`tkn hub install task git-clone --version 0.8`

## Create or configure the yaml files
```
kubectl apply -f tasks.yaml
kubectl apply -f pipeline.yaml
```

## The Command to run the cd-pipeline
```
tkn pipeline start cd-pipeline \
    -p repo-url="https://github.com/XiaoLIUau/wtecc-CICD_PracticeCode.git" \
    -p branch="main" \
    -w name=pipeline-workspace,claimName=pipelinerun-pvc \
    --showlog
```