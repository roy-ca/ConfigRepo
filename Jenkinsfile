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
                        deployableName:"PRD",
                        configFile:"configOne.json",
                        namePath:"main_demo",
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
                        applicationName:"Demo-Application",
                        changesetNumber:"${changeset}"
                    )
                }
            }
        }
    }
}
        
