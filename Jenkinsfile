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
                    //changeset = snDevOpsConfigUpload(applicationName:"AdoPublish Test",configFile:"configIni.ini",namePath:"TestCompOne/new/key",target:"component",dataFormat:"ini",autoCommit:false,autoValidate:false,autoPublish:false)
                    //snDevOpsConfigUpload(applicationName:"AdoPublish Test",changesetNumber:"${changeset}",configFile:"configXml.xml",namePath:"TestCompOne/new/key",target:"component",dataFormat:"xml",autoCommit:false,autoValidate:false,autoPublish:false)
                    snapshotObj=snDevOpsConfig(
                        applicationName:"AdoPublish Test",
                        configFile:"configOne.json",
                        namePath:"TestCompOne/new/key",
                        target:"component",
                        dataFormat:"json",
                        markFailed:false,
                        autoPublish:"true",
                        autoValidate:"true",
                        autoCommit:"true"
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
        
