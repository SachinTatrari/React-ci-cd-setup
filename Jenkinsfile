pipeline {
    agent any
    stages {
        stage('build'){
            agent{
                docker {
                    image 'node:18-alpine'
                    reuseNode true //Reuse the node for next stages
                }
            }

            steps{
                sh '''
                ls -l
                node --version
                npm --version
                npm install
                npm run build
                ls -l
                '''
            }

        }
        
        
    }
}