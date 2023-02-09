# Deploy to Kubernetes / OpenShift

This folder holds the files for the lab: _Deploy to Kubernetes_ which is part of the **IBM-CD0215EN-Skills Network Introduction to CI/CD** course.

## Optional Tool 
If working in the terminal becomes difficult because the command prompt is very long, you can shorten the prompt using the following command:

`export PS1="[\[\033[01;32m\]\u\[\033[00m\]: \[\033[01;34m\]\W\[\033[00m\]]\$ "`

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
## Check created tasks local and cluster level
```
tkn task ls
tkn clustertask ls 
```

## The command to run the cd-pipeline
```
tkn pipeline start cd-pipeline \
    -p repo-url="https://github.com/XiaoLIUau/wtecc-CICD_PracticeCode.git" \
    -p branch=main \
    -p app-name=hitcounter \
    -p build-image=image-registry.openshift-image-registry.svc:5000/sn-labs-xiaoliuconta/tekton-lab:latest \
    -w name=pipeline-workspace,claimName=pipelinerun-pvc \
    --showlog
```

## Check run pipeline and logs
```
tkn pipelinerun ls
tkn pipelinerun logs --last
```

## Check the deployment
`kubectl get all -l app=hitcounter`
