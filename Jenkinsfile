def changeset = ''
pipeline{
    agent any
    stages {
        stage('Upload'){
            steps{
                script{
                    changeset=snDevOpsConfigPipeline(
                        applicationName:"AdoPublish Test",
                        configFile:"configOne.json",
                        namePath:"TestCollOne/new/key",
                        deployableName:"Test",
                        target:"deployable",
                        autoCommit:true,
                        autoValidate:true,
                        dataFormat:"json",
                        autoPublish:false
                      )
                }
            }
        }
        stage('Register') {
             steps{
                 script {
                      snDevOpsConfigRegisterPipeline(changesetNumber:"${changeset}",applicationName:"AdoPublish Test")
                 }
             }
        }          
    }
}
        
