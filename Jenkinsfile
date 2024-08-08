pipeline{
    agent {
        label 'AGENT-1'
    }
    options{
        timeout(time: 30,unit: 'MINUTES')
        disableConcurrentBuilds()
        ansiColor('xterm')
    }
    environment{
        def appVersion = ''
        nexusUrl = 'nexus.muvva.online:8081'
    }
    parameters {
        string(name: 'appVersion', defaultValue: '${appVersion}', description: 'Reading version no. of artifact')
    }
    stages{
        stage('read the version'){
            steps{
                script{
                    echo "app version is: ${parms.appVersion}"
                }
            }
        }
        
     }
        post{
            always{
                echo "Running always"
                deleteDir()
            }
        }
    }