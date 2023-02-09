# Integrate Unit Test Automation

This folder holds the files for the lab: _Integrate Unit Test Automation_ which is part of the **IBM-CD0215EN-Skills Network Introduction to CI/CD** course.

## Establish the tasks
```
kubectl apply -f tasks.yaml
tkn hub install task git-clone
tkn hub install task flake8
```

## The command for start cd-pipeline
```
tkn pipeline start cd-pipeline \
    -p repo-url="https://github.com/XiaoLIUau/wtecc-CICD_PracticeCode.git" \
    -p branch="main" \
    -w name=pipeline-workspace,claimName=pipelinerun-pvc \
    --showlog
```