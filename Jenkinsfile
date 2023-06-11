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
                        namePath:"TestCollOne/new/key",
                        target:"component",
                        autoCommit:true,
                        autoValidate:true,
                        dataFormat:"json",
                        autoPublish:false
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
            junit '**/*.xml'
        }
    }
}
        
