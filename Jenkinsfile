pipeline {
    agent any
    stages {
        stage('Prepare') {
            steps {
                script {
                    // Set a custom npm cache directory
                    sh 'npm config set cache /tmp/.npm --global'
                    
                }
            }
        }
        stage('build'){
            agent{
                docker {
                    image 'node:18-alpine'
                    // reuseNode true //Reuse the node for next stages
                    args '--mount type=volume,source=.npm,target=/tmp/.npm'

                }
            }

            steps{
                sh '''
                ls -l
                node --version
                npm --version
                npm run build
                ls -l
                '''
            }

        }
        
        
    }
}