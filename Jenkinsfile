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
        stage('getDetails'){
            steps{
                script{
                getResult = snDevOpsConfigValidate(applicationName:"DevOpsChangeFour",deployableName:null,changesetNumber:"${changeset}")
                echo "!!!!!!! getResult:: ${getResult}" 
                }
            }
    }
        stage('register'){
            steps{
                script{
                snDevOpsConfigRegisterPipeline(applicationName:"DevOpsChangeFour",changesetNumber:"${changeset}")
                }
            }
        }
        }
}
