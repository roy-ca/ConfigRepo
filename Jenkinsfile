def changeset = ''
def getResult =''
pipeline{
    agent any
    stages {
        stage('Upload'){
            steps{
                script{
                    changeset=snDevOpsConfigUpload(
                        applicationName:"MultfolderDemoApp",
                        deployableName:"Test",
                        configFile:"config.json",
                        namePath:"multiSlash_demo",
                        target:"deployable",
                        autoCommit:true,
                        autoValidate:true,
                        dataFormat:"json"
                      )
                }
            }
        }           
        stage('Register'){
            steps{
                script{
                    snDevOpsConfigRegisterPipeline(
                        applicationName:"MultfolderDemoApp",
                        changesetNumber:"${changeset}"
                    )
                }
            }
        }
    }
}
        
