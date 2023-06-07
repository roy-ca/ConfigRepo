def changeset = ''
pipeline{
    agent any
    stages {
        stage('Upload'){
            steps{
                script{
                    changeset=snDevOpsConfigUpload(
                        applicationName:"AdoPublish Test",
                        configFile:"configOne.json",
                        namePath:"TestCompOne/testRun",
                        target:"component",
                        autoCommit:true,
                        autoValidate:true,
                        dataFormat:"json"
                      )
                }
            }
        }           
    }
}
        
