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
                    changeset = snDevOpsConfigUpload(applicationName:"TrialApp",configFile:"Config/*.json",namePath:"TestCompOne/new/key",target:"deployable",deployableName:"Development_1",dataFormat:"json",autoCommit:true,autoValidate:true,autoPublish:true)
                }
            }
        }
        stage('export') {
            steps{
                snDevOpsConfigExport(applicationName:"TrialApp",deployableName:"Development_1",exporterName:"returnAllData-now",exporterFormat:"json",showResults:true,fileName:"")
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
        
