def changeset = ''
pipeline{
    agent any
    stages {
        stage('Upload'){
            steps{
                script{
                    changeset = snDevOpsConfigUpload(applicationName:"TrialApp",configFile:"Config",namePath:"TestCompOne/new/multiFile",target:"deployable",deployableName:"Development_1",dataFormat:"ini",autoCommit:true,autoValidate:true,autoPublish:true)
                }
                echo "${changeset}"
            }
        }
    }
}
        
