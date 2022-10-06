def changeset = ''
def getResult =''
pipeline{
    agent any
    stages {
        stage('upload') {
            steps{
                script{
                  changeset = snDevOpsConfigUpload(applicationName:"Demo-Application",deployableName:"Prod-Hyd",target:"deployable",namePath:"test_branch",dataFormat:"json",autoCommit:true,autoValidate:true,configFile:"configOne.json")
                    echo "Changeset NUmber ::  ${changeset}"
                }       }    }
        stage('validate'){
            steps{
                script{
                getResult = snDevOpsConfigValidate(applicationName:"Demo-Application",deployableName:"Prod-Hyd")
                echo "!!!!!!! getResult:: ${getResult}" 
                }
            }
    }
        stage('register'){
            steps{
                script{
                snDevOpsConfigRegisterPipeline(applicationName:"Demo-Application",changesetNumber:"${changeset}")
                }
            }
        }
        }
}
        
