pipeline {
    agent any
    
    stages {
        stage('Clone'){
            steps {
                git 'https://github.com/moeruuu/mern-amazona-cicd'
            }
        }
        
        stage('Install frontend'){
            steps {
             dir('frontend') {
                 sh 'npm install'
             }   
            }
        }
        
        stage('Install Backend'){
            steps {
                dir('backend'){
                    sh 'npm install'
                }
            }
        }
        
        stage('Build Docker') {
            steps {
                sh 'docker compose build'
            }
        }
        
        stage('Deploy') {
            steps {
                sh 'docker compose down'
                sh 'docker compose up -d'
            }
        }
    }
}
