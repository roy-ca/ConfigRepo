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
                    changeset = snDevOpsConfigGetSnapshots(applicationName:"TrialApp",deployableName:null,changesetNumber:"Chset-31",isValidated:true,continueWithLatest:true)
                }
                echo "${changeset}"
            }
        }
    }
}
        
