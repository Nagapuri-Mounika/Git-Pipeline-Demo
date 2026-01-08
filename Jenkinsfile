node {

    stage('Checkout') {
        echo 'Checking out code'
        git branch: 'main',
            url: 'https://github.com/Nagapuri-Mounika/Git-Pipeline-Demo.git'
    }

    stage('Build') {
        echo 'Building project'
        sh 'chmod +x build.sh'
        sh './build.sh'
    }

    stage('Test') {
        echo 'Running tests'
        sh 'java -cp src/main/java com.example.HelloDevOpsTest'
    }

    stage('Archive') {
        echo 'Archiving artifact'
        archiveArtifacts artifacts: 'app.jar', fingerprint: true
    }
}
