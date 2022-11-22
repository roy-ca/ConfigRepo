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
                        deployableName:"TST-2",
                        configFile:"configThree.json",
                        namePath:"test_demo",
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
        
