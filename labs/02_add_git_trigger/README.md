# Adding GitHub Triggers

This folder holds the files for the lab: _Adding GitHub Triggers_ which is part of the **IBM-CD0215EN-Skills Network Introduction to CI/CD** course.

# To start the pipeline run 
## Set port for listener in localhost
`kubectl port-forward service/el-cd-listener  8090:8080`

## Command to set a trigger
In a new terminal, run following curl command:

`
curl -X POST http://localhost:8090 \
  -H 'Content-Type: application/json' \
  -d '{"ref":"main","repository":{"url":"https://github.com/XiaoLIUau/wtecc-CICD_PracticeCode"}}'
`
