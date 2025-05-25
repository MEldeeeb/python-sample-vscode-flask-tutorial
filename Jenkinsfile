node('bash') {
    stage('Build Docker image') {
        sh "docker build -t meldeeeb/l_2:v${env.BUILD_NUMBER} ."
    }
    
    stage('Push Docker image') {
        sh "docker push meldeeeb/l_2:v${env.BUILD_NUMBER}"
    }
}