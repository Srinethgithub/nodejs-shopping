pipeline {
    agent any

    stages {
        stage('git checkout') {
            steps {
                git branch: 'master',
                url: 'https://github.com/Srinethgithub/nodejs-shopping.git'
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
