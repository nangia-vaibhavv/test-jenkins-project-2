pipeline {
    agent { label 'wn'}

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
        stage('Docker login') {
            steps {
                withCredentials([usernamePassword(credentialsId: 'docker-creds', passwordVariable: 'DOCKER_PASSWORD', usernameVariable: 'DOCKER_USERNAME')]) {
                    echo('username ${DOCKER_USERNAME}')
                    sh 'docker login -u $DOCKER_USERNAME -p $DOCKER_PASSWORD'
                }
            }
        }
        stage('Docker build') {
            steps {
                echo('compile build')
                sh 'docker build -t vn2001/testjenkinsproject2:latest .'
            }
        }
        stage('Docker run') {
            steps {
                echo('docker run')
                sh 'docker run -d vn2001/testjenkinsproject2:latest'
            }
        }
        stage('Docker push') {
            steps {
                echo('docker push')
                sh 'docker push vn2001/testjenkinsproject2:latest'
            }
        }
    }
}