def changeset = ''
def getResult =''
pipeline{
    agent any
    stages {
        stage('validate') {
            steps{
                script{
                  snDevOpsConfigValidate(applicationName:"DevOpsChangeFour",deployableName:"PRD",snapshotName:"PRD-v8.dpl")
                    sleep 3
                }       }    }
        stage('publish') {
            steps {
                snDevOpsConfigPublish(applicationName:"DevOpsChangeFour",deployableName:"PRD",snapshotName:"PRD-v7.dpl")
                sleep 3
            }
        }
        stage('register'){
            steps{
                script{
                snDevOpsConfigRegisterPipeline(applicationName:"DevOpsChangeFour",snapshotName:"PRD-v4.dpl")
                }
            }
        }
        }
}
