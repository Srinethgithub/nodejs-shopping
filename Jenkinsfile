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
        stage('docker build image') {
            steps {
                sh 'docker build -t nodejs-shopping-app .'
            }
        }

        stage('run container') {
            steps {
                sh 'docker run -d -p 3000:3000 --name shopping-container nodejs-shopping-app'
            }
        }
    }
}
