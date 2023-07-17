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
                    changeset = snDevOpsConfigGetSnapshots(applicationName:"TrialApp",deployableName:"Development_1",changesetNumber:null,isValidated:true)
                }
                echo "${changeset}"
            }
        }
    }
}
        
