pipeline {
    agent any

    tools {
        jdk 'jdk11'
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/Nagapuri-Mounika/Git-Pipeline-Demo.git'
                echo 'Repository cloned successfully'
            }
        }

        stage('Build') {
            steps {
                echo 'Building application...'
                sh 'chmod +x build.sh'
                sh './build.sh'
            }
        }

        stage('Archive') {
            steps {
                echo 'Archiving artifacts...'
                archiveArtifacts artifacts: 'app.jar', fingerprint: true
                archiveArtifacts artifacts: 'build.sh', fingerprint: true
            }
        }
    }

    post {
        always {
            echo 'Pipeline completed'
            cleanWs()
        }
    }
} EOF

