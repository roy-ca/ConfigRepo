def getResult =''
pipeline{
    agent any
    stages {
        stage('getDetails'){
            steps{
                script{
                getResult = snDevOpsConfigUpload(applicationName:"DevOpsChangeFour",deployableName:"PRD",target:"deployable",configFile:"configOne.json",dataFormat:"json",namePath:"trial",autoCommit:true,autoValidate:true)
                echo "!!!!!!! getResult:: ${getResult}" 
                }
            }
    }
        stage('register'){
            steps{
                snDevOpsConfigRegisterPipeline(applicationName:"DevOpsChangeFour",changesetNumber:"${getResult}")
            }
        }
        }
}
