pipeline
{
    agent any
    stages
    {
        stage ('Checkout Script From Git') {
            steps {
                dir('depscripts') {
                    git url: 'git@github.com:tawandaEsure/jenkins-local-bogus.git'
                    echo 'Checkout From Git - deployment scripts stage done...'
                }
            }
        }
        stage('Build') {
            steps {
                // Run the maven build
                nodejs(nodeJSInstallationName: 'nodeJS') {
                    
                    sh 'node -v'
                    
                }
                
                echo 'Build stage done...'
            }
        }
    }
    post
    {
        success
        {
            echo 'SUCCESS'
            slackSend (color: '#00FF00', message: "SUCCESSFUL => JOB ::  '${env.JOB_NAME} [${env.BUILD_NUMBER}]' (${env.BUILD_URL})")
        }
        failure
        {
            echo 'Result...'
            echo 'FAILED'
        }
    }
}
