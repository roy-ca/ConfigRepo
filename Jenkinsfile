def changeset = ''
def getResult =''
pipeline{
    agent any
    stages {
        stage('validate') {
            steps{
                script{
                  snDevOpsConfigValidate(applicationName:"DevOpsChangeFour",deployableName:"PRD",snapshotName:"PRD-v3.dpl")
                    sleep 1
                }       }    }
        stage('publish') {
            steps {
                snDevOpsConfigPublish(applicationName:"DevOpsChangeFour",deployableName:"PRD",snapshotName:"PRD-v2.dpl")
                sleep 1
            }
        }
        stage('register'){
            steps{
                script{
                snDevOpsConfigRegisterPipeline(applicationName:"DevOpsChangeFour",snapshotName:"PRD-v2.dpl")
                }
            }
        }
        }
}
