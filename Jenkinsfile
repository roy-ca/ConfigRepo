def changeset = ''
def getResult =''
pipeline{
    agent any
    stages {
        stage('Upload'){
            steps{
                script{
                    changeset=snDevOpsConfigUpload(
                        applicationName:"DevOpsChangeFour",
                        collectionName:"release-1.5",
                        configFile:"configOne.json",
                        namePath:"collection_demo",
                        target:"collection",
                        autoCommit:false,
                        autoValidate:true,
                        dataFormat:"json"
                      )
                    snDevOpsConfigUpload(
                        applicationName:"DevOpsChangeFour",
                        collectionName:"release-1.0",
                        configFile:"config.json",
                        namePath:"collection_sub",
                        target:"collection",
                        autoCommit:true,
                        autoValidate:true,
                        dataFormat:"json",
                        changesetNumber:"${changeset}"
                      )
                }
            }
        }           
        stage('Register'){
            steps{
                script{
                    snDevOpsConfigRegisterPipeline(
                        applicationName:"DevOpsChangeFour",
                        changesetNumber:"${changeset}"
                    )
                }
            }
        }
    }
}
        
