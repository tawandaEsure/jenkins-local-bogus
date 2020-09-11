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
                    sh 'npm -v'
                    sh 'npm i'
                }
                
                echo 'Build stage done...'
            }
        }
    }
}
