pipeline {
    agent any

    stages {
        stage('git checkout') {
            steps {
                checkout scmGit(branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[credentialsId: 'Srinethid7', url: 'https://github.com/Srinethgithub/nodejs-shopping.git']])
            }
        }
        stage('installing') {
            steps {
                sh 'npm ci'
            }
        }
        stage('test') {
            steps {
                sh 'npm test'
            }
        }  
        stage('build') {
            steps {
                sh 'npm run build'
            }
        }    
    }
}
