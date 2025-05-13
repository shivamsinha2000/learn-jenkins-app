pipeline {
    agent any

    stages {
        stage('w/o docker') {
            steps {
                sh '''
                    echo "w/o docker"
                    ls -la
                    touch container-no.txt
                    '''
            }
        }    
        stage('w/ docker') {
            agent {
                docker {
                    image 'node:18-alpine'
                    reuseNode true
                }
            }
            steps {
                sh '''
                    echo "w/ docker"
                    ls -la
                    touch container-yes.txt
                    '''
            }
        }
    }
}
