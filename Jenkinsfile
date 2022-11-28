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
                        autoCommit:false,
                        autoValidate:true,
                        dataFormat:"json"
                      )
                     snDevOpsConfigUpload(
                        applicationName:"DevOpsChangeFour",
                        changesetNumber:"${changeset}",
                        deployableName:"TST-1",
                        configFile:"config.json",
                        namePath:"main_demo",
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
                        applicationName:"DevOpsChangeFour",
                        changesetNumber:"${changeset}"
                    )
                }
            }
        }
    }
}
        
