def changeset = ''
def getResult =''
pipeline{
    agent any
    stages {
        stage('upload') {
            steps{
                script{
                  changeset = snDevOpsConfigUpload(applicationName:"DevOpsChangeFour",deployableName:"PRD",target:"deployable",namePath:"getSnapshot",dataFormat:"json",autoCommit:true,autoValidate:true,configFile:"configOne.json")
                    echo "Changeset NUmber ::  ${changeset}"
                }       }    }
        stage('register'){
            steps{
                script{
                snDevOpsConfigRegisterPipeline(applicationName:"DevOpsChangeFour",changesetNumber:"${changeset}")
                }
            }
        }
        }
}
