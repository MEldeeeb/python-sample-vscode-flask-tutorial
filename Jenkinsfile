node('bash') {
    stage('Build Docker Image') {
        sh "docker build -t meldeeeb/l_2_scriptive:v${env.BUILD_NUMBER} ."
    }
    
    stage('Push Docker Image') {
        sh "docker push meldeeeb/l_2_scriptive:v${env.BUILD_NUMBER}"
    }
}