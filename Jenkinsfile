def snapshotObj = ''
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
                    snapshotObj=snDevOpsConfigPipeline(
                        applicationName:"AdoPublish Test",
                        configFile:"configOne.json",
                        namePath:"TestCompOne/new/key",
                        target:"component1",
                        dataFormat:"json",
                        autoPublish:true,
                        outputFormat:"xml",
                        markFailed:true
                      )
                    echo "Final Obj"
                    echo "${snapshotObj}"
                }
            }
        }
    }
    post{
        always{
            echo ">>>>>Displaying Test results"
            junit '**/*_${BUILD_NUMBER}.xml'
        }
    }
}
        
