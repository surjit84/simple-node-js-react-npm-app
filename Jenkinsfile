pipeline {
    agent {label 'master'}
    tools {nodejs 'N1'}    
    environment {
        CI = 'true'
    }
    stages {
        stage('Build') {
            steps {
                sh 'npm install'
                sh 'npm build'
            }
        }
        stage('Test') {
            steps {
                sh 'npm test'
            }
        }
        stage('Test') {
            steps {
                sh 'npm pack'
            }
        }
        stage('Deliver') {
            steps {
                input message: 'Finished using the web site? (Click "Proceed" to continue)'
                sh 'npm start'
            }
        }
    }
}
