pipeline{
    agent{
        label "bash"
    }
    stages{
        stage("build Docker image"){
            steps{
                sh "docker build -t meldeeeb/lab_2:v${BUILD_NUMBER} ."
            }
        }

        }
    }
}