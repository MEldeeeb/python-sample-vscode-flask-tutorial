pipeline{
    agent{
        label "bash"
    }
    stages{
        stage("build Docker image"){
            steps{
                sh "docker build -t meldeeeb/l_2:v${BUILD_NUMBER} ."
            }
        }
        stage("Push Docker image"){
            steps{
                sh "docker push meldeeeb/l_2:v${BUILD_NUMBER}"
            }
        }
    }
}