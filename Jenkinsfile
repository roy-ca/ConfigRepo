def changeset = ''
pipeline{
    agent any
    stages {
        stage('Register'){
            steps{
                sleep 3
            }
        }
        stage('Upload'){
            steps{
                script{
                    changeset = snDevOpsConfig(applicationName:"TrialApp",deployableName:"Development_1",isValidated:false,continueWithLatest:true,target:"deployable",namePath:"test/NoIMpact",configFile:"config.json",dataFormat:"json")
                }
                echo "${changeset}"
            }
        }
    }
}
        
