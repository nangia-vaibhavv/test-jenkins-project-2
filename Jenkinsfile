pipeline {
    agent any
    stages {
        stage('Build') {
            echo('Build started')
            sh 'mvn clean package'
        }
        stage('Test') {
            echo('test started')
            sh 'mvn test'
        }
        stage('Compile') {
            echo('compile started')
            sh 'mvn compile'
        }
    }
}