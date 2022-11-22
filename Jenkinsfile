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
                        deployableName:"TST-1",
                        configFile:"config.json",
                        namePath:"multiSlash_demo",
                        target:"deployable",
                        autoCommit:true,
                        autoValidate:true
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
        
