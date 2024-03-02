

pipeline {
    agent {
        docker {
            image 'node:lts-buster-slim'
            args '-p 3000:3000 -p 5000:5000' 
        }   
    }
    environment {
        CI = 'true'
    }
    stages {
        stage('Build') {
            steps {
                sh 'npm install'
              /*  sh 'npm cache clean --force'
                sh 'npm install --verbose'  */
            }
        }    
        stage('Test') {
            steps {
                sh './jenkins/scripts/test.sh'
            }
        }
    }
}


