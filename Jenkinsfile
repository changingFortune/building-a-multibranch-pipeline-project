pipeline {
    // agent { 
    // 	docker {
    //         image 'node:8.9.4'
    //         args '-p 4001:3000'
    //     }
    // }
    // environment {
    //     CI = 'true'
    // }
    agent any
    stages {
        stage('Build') {
            steps {
                // sh 'npm install'
                sh 'echo what'
            }
        }
        stage('Test') {
            steps {
                sh './jenkins/scripts/test.sh'
            }
        }
        stage('Deliver') {
            steps {
                sh './jenkins/scripts/deliver-for-development.sh'
                input message: 'Finished using the web site? (Click "Proceed" to continue)'
                sh './jenkins/scripts/kill.sh'
            }
        }
    }
}