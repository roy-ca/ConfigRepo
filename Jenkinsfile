def changeset = ''
def getResult =''
pipeline{
    agent any
    stages {
        stage('validate') {
            steps{
                script{
                  snDevOpsConfigUpload(applicationName:"DevOpsChangeFour",deployableName:"PRD",target:"deployable",dataFormat:"json",configFile:"configOne.json",namePath:"spike",autoCommit:true,autoValidate:false)
                    sleep 3
                }       }    }
        stage('publish') {
            steps {
                snDevOpsConfigValidate(applicationName:"DevOpsChangeFour",deployableName:"PRD",snapshotName:"PRD-v1.dpl")
                sleep 3
            }
        }
        stage('register'){
            steps{
                script{
                snDevOpsConfigRegisterPipeline(applicationName:"DevOpsChangeFour",snapshotName:"PRD-v1.dpl")
                }
            }
        }
        }
}
