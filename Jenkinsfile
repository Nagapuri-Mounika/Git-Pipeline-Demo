node {

    stage('Checkout') {
        echo 'Checking out code from GitHub'
        git branch: 'main',
            url: 'https://github.com/Nagapuri-Mounika/Git-Pipeline-Demo.git'
    }

    stage('Build & Test') {
        echo 'Building and testing the project'
        sh 'chmod +x build.sh'
        sh './build.sh'
    }

    stage('Archive') {
        echo 'Archiving build artifact'
        archiveArtifacts artifacts: 'app.jar', fingerprint: true
    }
}
