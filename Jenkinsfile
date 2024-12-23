pipeline {
    agent {
        docker {
            image 'node:16-buster-slim' 
            args '-p 3000:3000' 
        }
    }
    stages {
        stages('Build') { 
            steps {
                sh 'npm install'
            }
        }
        stages {
            stages('Test') {
                steps {
                    sh "chmod +x -R ${env.WORKSPACE}"
                    sh './jenkins/scripts/test.sh'
                }
            }
        }
    }
}