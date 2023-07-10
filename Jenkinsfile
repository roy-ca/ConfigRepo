def snapshotObj = ''
def changeset = ''
pipeline{
    agent any
    stages {
        stage('Pre'){
            steps {
                echo 'Pre exist'
                sleep 3
            }
        }
        stage('Upload'){
            steps{
                script{
                    changeset = snDevOpsConfigUpload(applicationName:"TrialApp",configFile:"config.json",namePath:"TestCompOne/new/key",target:"deployable",deployableName:"Development_1",dataFormat:"json",autoCommit:true,autoValidate:true,autoPublish:true)
                }
            }
        }
        stage('Register') {
            steps{
                snDevOpsConfigRegisterPipeline(applicationName:"TrialApp",changesetNumber:"${changeset}")
            }
        }
    }
    //post{
      //  always{
        //    echo ">>>>>Displaying Test results"
          //  junit '**/*_${BUILD_NUMBER}.xml'
        //}
    //}
}
        
