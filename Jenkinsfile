pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/poojareddy24817/Java.git'
            }
        }

        stage('Build') {
            steps {
                bat 'javac HelloWorld.java'
            }
        }

        stage('Run') {
            steps {
                bat 'java -cp . HelloWorld > hello_output.txt'
            }
        }

        stage('Archive') {
            steps {
                archiveArtifacts artifacts: 'HelloWorld.class, hello_output.txt', fingerprint: true
            }
        }
    }

    post {
        always {
            echo "Pipeline finished."
        }
    }
}
