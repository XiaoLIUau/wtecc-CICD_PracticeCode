# Create a base pipeline

This folder holds the files for the lab _Create a Base Pipeline_ which is part of the **IBM-CD0215EN-Skills Network Introduction to CI/CD** course.

# Commands to creat CI/CD in Kubernetes
`kubectl apply -f tasks.yaml`

`kubectl apply -f pipeline.yaml`

# Command to run the pipeline using Tekton
```
tkn pipeline start cd-pipeline \
    --showlog \
    -p repo-url="https://github.com/xiaoLIUau/wtecc-CICD_PracticeCode.git" \
    -p branch="main"
```
