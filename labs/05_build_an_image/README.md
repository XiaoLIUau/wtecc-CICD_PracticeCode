# Building an Image

This folder holds the files for the lab: _Building an Image_ which is part of the **IBM-CD0215EN-Skills Network Introduction to CI/CD** course.

## The command to install tasks from Tekton Hub:
```
tkn hub install task git-clone --version 0.8`
tkn hub install task flake8
```
## Create or configure the yaml files
```
kubectl apply -f tasks.yaml
kubectl apply -f pipeline.yaml
kubectl apply -f pvc.yaml
```

## The command to run the cd-pipeline
```
tkn pipeline start cd-pipeline \
    -p repo-url="https://github.com/XiaoLIUau/wtecc-CICD_PracticeCode.git" \
    -p branch=main \
    -p build-image=image-registry.openshift-image-registry.svc:5000/$SN_ICR_NAMESPACE/tekton-lab:latest \
    -w name=pipeline-workspace,claimName=pipelinerun-pvc \
    --showlog
```

## Check run pipeline and logs
```
tkn pipelinerun ls
tkn pipelinerun logs --last
```