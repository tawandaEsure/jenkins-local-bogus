pipeline
{
    agent any
    tools
    {
        nodejs 'nodeJS'
    }
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
        stage('Install') {
            steps {
                sh 'node -v'
                sh 'npm -v'
                sh 'npm i'
                echo 'Install stage done...'
            }
        }
        stage('Test') {
            steps {
                sh 'npm run test --no-watch --no-progress --browsers=ChromeHeadlessNoSandbox --forceExit'
                echo 'Test stage done...'
            }
        }
        stage('Publish') {
            steps {
                sh 'npm publish'
                echo 'Publish stage done...'
            }
        }
    }
}
