def changeset = ''
def getResult =''
pipeline{
    agent any
    stages {
        stage('upload') {
            steps{
                script{
                 changeset=snDevOpsConfigUpload(applicationName:"Demo-Application",deployableName:"Prod-Hyd",target:"deployable",dataFormat:"json",configFile:"configOne.json",namePath:"main_branch",autoCommit:true,autoValidate:false)
                    sleep 3
                }       }    }
        stage('publish') {
            steps {
                snDevOpsConfigValidate(applicationName:"Demo-Application",deployableName:"Prod-Hyd")
                sleep 3
            }
        }
        stage('register'){
            steps{
                script{
                snDevOpsConfigRegisterPipeline(applicationName:"Demo-Application",changesetNumber:"${changeset}")
                }
            }
        }
        }
}
