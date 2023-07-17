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
                    changeset = snDevOpsConfigGetSnapshots(applicationName:"TrialApp",deployableName:null,changesetNumber:"Chset-33",isValidated:true)
                }
                echo "${changeset}"
            }
        }
    }
}
        
