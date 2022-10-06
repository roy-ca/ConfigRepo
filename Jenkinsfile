def changeset = ''
def getResult =''
pipeline{
    agent any
    stages {
        stage('Upload') {
            steps {
                script{
                  changeset = snDevOpsConfigUpload(
                      applicationName: "Demo-Application",
                      deployableName: "Prod-Hyd",
                      target: "deployable",
                      namePath: "test_branch",
                      dataFormat: "json",
                      autoCommit: true,
                      autoValidate: true,
                      configFile: "config.json"
                  )
                  echo "Changeset Number ::  ${changeset}"
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
        
