pipeline
{
    agent any
    tools { nodejs 'node' }

    stages
    {
        stage ('Checkout Script From Git')
        {
            steps
            {
                dir('depscripts') {
                    git url: 'git@github.com:tawandaEsure/jenkins-local-bogus.git'
                    echo 'Checkout From Git - deployment scripts stage done...'
                }
            }
        }
        stage('Build') {
            steps {
                // Run the maven build

                echo 'Build stage done...'
                 nodejs(nodeJSInstallationName: 'Node 6.x', configId: '<config-file-provider-id>') {
                    sh 'npm config ls'
                }
            }
        }
    }
    post
    {
        success
        {
            echo 'SUCCESS'
        }
        failure
        {
            echo 'Result...'
            echo 'FAILED'
        }
    }
}
