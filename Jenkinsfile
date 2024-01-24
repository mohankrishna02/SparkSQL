pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build JAR') {
            steps {
                script {
                    sh 'mvn clean package' // Use 'mvn' or 'gradle' depending on your build tool
                }
            }
        }
    }

    post {
        success {
            archiveArtifacts 'target/*.jar' // Adjust the path based on your project structure
        }
    }
}
