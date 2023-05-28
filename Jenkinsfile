def changeset = ''
def getResult =''
pipeline{
    agent any
    stages {
        stage('Upload'){
            steps{
                script{
                    changeset=snDevOpsConfigUpload(
                        applicationName:"AdoPublish Test",
                        deployableName:"Test",
                        configFile:"configOne.json",
                        namePath:"TestCompOne/testRun",
                        target:"deployable",
                        autoCommit:true,
                        autoValidate:true,
                        dataFormat:"json"
                      )
                }
            }
        }           
        stage('Get Snapshot'){
            steps {
                script {
                    getResult =  snDevOpsConfigGetSnapshots(applicationName:"AdoPublish Test",deployableName:"Test")
                }
                echo getResult
            }
        }
    }
}
        
