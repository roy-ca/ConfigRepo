def changeset = ''
def getResult =''
pipeline{
    agent any
    stages {
        stage('validate') {
            steps{
                script{
                  snDevOpsConfigValidate(applicationName:"DevOpsChangeFour",deployableName:"TST-1",snapshotName:"TST-1-v1.dpl")
                }       }    }
        stage('publish') {
            steps {
                snDevOpsConfigPublish(applicationName:"DevOpsChangeFour",deployableName:"PRD",snapshotName:"PRD-v1.dpl")
            }
        }
        stage('register'){
            steps{
                script{
                snDevOpsConfigRegisterPipeline(applicationName:"DevOpsChangeFour",changesetNumber:"Chset-3")
                }
            }
        }
        }
}
