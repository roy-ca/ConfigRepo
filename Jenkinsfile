def changeset = ''
def getResult =''
pipeline{
    agent any
    stages {
        stage('upload') {
            steps{
                script{
                  changeset = snDevOpsConfigUpload(applicationName:"DevOpsChangeFour",deployableName:"TST-1",target:"deployable",namePath:"getSnapshot",dataFormat:"json",autoCommit:true,autoValidate:true,configFile:"configOne.json")
                    echo "Changeset NUmber ::  ${changeset}"
                }       }    }
        stage('getDetails'){
            steps{
                script{
                getResult = snDevOpsConfigGetSnapshots(applicationName:"DevOpsChangeFour",deployableName:"TST-1",changesetNumber:null)
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
        
