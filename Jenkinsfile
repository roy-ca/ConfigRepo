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
                        namePath:"vars/collection_demo",
                        target:"collection",
                        autoCommit:false,
                        autoValidate:true,
                        dataFormat:"json"
                      )
                    snDevOpsConfigUpload(
                        applicationName:"DevOpsChangeFour",
                        deployableName:"PRD",
                        configFile:"config.json",
                        namePath:"vars/prod_sub",
                        target:"deployable",
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
        
