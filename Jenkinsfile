pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo('Build started')
                sh 'mvn clean package'
            }
        }
        stage('Test') {
            steps {
                echo('test started')
                sh 'mvn test'
            }
        }
        stage('Compile') {
            steps {
                echo('compile started')
                sh 'mvn compile'
            }
        }
    }
}