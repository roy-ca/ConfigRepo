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
                snDevOpsConfigRegisterPipeline(applicationName:"DevOpsChangeFour",changesetNumber:"Chset-6")
            }
        }
        }
}
