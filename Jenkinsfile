def changeset = ''
def getResult =''
pipeline{
    agent any
    stages {
        stage('Upload - Main Branch') {
            when {
                branch "main"
            }
            steps {
                git branch: 'main', url: 'https://github.com/roy-ca/ConfigRepo.git'
                script{
                  changeset = snDevOpsConfigUpload(
                      applicationName: "Demo-Application",
                      deployableName: "Prod-Hyd",
                      target: "deployable",
                      namePath: "main_branch",
                      dataFormat: "json",
                      autoCommit: true,
                      autoValidate: false,
                      configFile: "configOne.json"
                  )
                  echo "Changeset Number ::  ${changeset}"
                }       
            }    
        }
        stage('Upload - Test Branch') {
            when {
                branch "test"
            }
            steps {
                git branch: 'test', url: 'https://github.com/roy-ca/ConfigRepo.git'
                script{
                  changeset = snDevOpsConfigUpload(
                      applicationName:"Demo-Application",
                      deployableName:"Prod-Hyd",
                      target:"deployable",
                      namePath:"test_branch",
                      dataFormat:"json",
                      autoCommit: true,
                      autoValidate: false,
                      configFile:"config.json"
                  )
                  echo "Changeset Number ::  ${changeset}"
                }       
            }    
        }
        stage('Validate') {
            steps{
                script{
                    getResult = snDevOpsConfigValidate(
                        applicationName: "Demo-Application",
                        deployableName: "Prod-Hyd"
                    )
                    echo "!!!!!!! getResult:: ${getResult}" 
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
