pipeline {
    agent any
    stages {
        stage('build') {
            nodejs(nodeJSInstallationName: 'nodejs') {
                steps{
                    sh 'npm install'
                }
            }
        }
        stage('deploy') {
            steps {
                nodejs(nodeJSInstallationName: 'nodejs') {
                    withAWS(credentials: 'aws-credentials') {
                        sh 'serverless deploy'
                    }
                }
            }
        }
    }
}