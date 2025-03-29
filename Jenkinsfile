pipeline {
    agent any
    tools {
        maven 'maven'  
    stages {
        stage('Build') {
            steps {
                bat 'mvn clean package'
            }
        }
        stage('Test') {
            steps {
                bat 'mvn test'
            }
        }
        stage('Run JAR') {
            steps {
                script {
                   
                    def output = bat(script: 'java -jar target/simple-java-project-1.0-SNAPSHOT.jar', returnStdout: true).trim()

                   
                    echo "Output from JAR: ${output}"
                }
            }
        }
    }
    }
}
