def changeset = ''
pipeline{
    agent any
    stages {
        stage('Upload'){
            steps{
                script{
                    changeset = snDevOpsConfigUpload(applicationName:"TrialApp",configFile:"Config/C*",namePath:"TestCompOne/new/multiFile",target:"deployable",deployableName:"Development_1",dataFormat:"",autoCommit:true,autoValidate:true,autoPublish:true)
                }
                echo "${changeset}"
            }
        }
    }
}
        
