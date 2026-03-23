pipeline {
    agent any
    tools {
        gradle 'Gradle'
        jdk 'JDK'
    }
    stages {
        stage('Checkout') {
            steps {
                git branch: 'master', url: 'https://github.com/adithyaS360/labinternaldevops.git'
            }
        }

        stage('Build') {
            steps {
                sh 'gradle build'  // Run Maven build
            }
        }

        stage('Test') {
            steps {
                sh 'gradle test'  // Run unit tests
            }
        }
     
        stage('Run Application') {
            steps {
                sh 'gradle display'
            }
        }

        
    }

    post {
        success {
            echo 'Build and deployment successful!'
        }
        failure {
            echo 'Build failed!'
        }
    }

}
