def getResult =''
pipeline{
    agent any
    stages {
        stage('getDetails'){
            steps{
                script{
                getResult = snDevOpsConfigValidate(applicationName:"DevOpsChangeFour",deployableName:"TST-1")
                echo "!!!!!!! getResult:: ${getResult}" 
                }
            }
    }
        stage('register'){
            steps{
                snDevOpsConfigRegisterPipeline(applicationName:"DevOpsChangeFour",snapshotName:"TST-1-v1.dpl")
            }
        }
        }
}
