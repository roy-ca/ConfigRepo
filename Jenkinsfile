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
                      collectionName: "testCollection",
                      target: "collection",
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
        
