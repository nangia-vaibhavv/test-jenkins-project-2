pipeline {
    agent any
    stages {
        stage('Debug Environment') {
            steps {
                sh 'java -version'
                sh 'mvn -version'
                sh 'echo $JAVA_HOME'
            }
        }
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