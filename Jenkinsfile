def getResult =''
pipeline{
    agent any
    stages {
        stage('register'){
            steps{
                snDevOpsConfigRegisterPipeline(applicationName:"testApp",snapshotName:"da")
            }
        }
        stage('getDetails'){
            steps{
                script{
                getResult = snDevOpsConfigGetSnapshots(applicationName:"testApp",deployableName: "TST-1",changesetNumber: null,outputFormat:"xml",isValidated:false)
                echo "!!!!!!! getResult:: ${getResult}" 
                }
            }
    }}
    post {
        always {
            junit checksName: "test",testResults:'*.xml'
        }
    }
}
        
