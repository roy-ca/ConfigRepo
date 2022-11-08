def changeset = ''
def getResult =''
pipeline{
    agent any
    stages {
        stage('Upload') {
            steps {
                script{
                  changeset = snDevOpsConfigUpload(
                      applicationName: "RoyTestApp",
                      collectionName: "testComponent",
                      target: "component",
                      namePath: "main",
                      dataFormat: "json",
                      autoCommit: true,
                      autoValidate: true,
                      configFile: "configOne.json"
                  )
                  echo "Changeset Number ::  ${changeset}"
                }       
            }    
        }
    }
}
        
