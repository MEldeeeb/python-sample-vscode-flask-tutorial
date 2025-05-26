@Library('libx@main')_

pipeline{
    agent{
        label "bash"
    }
    environment{
        DOCKER_USER = credentials('dockerhub-user')
        DOCKER_PASS = credentials('dockerhub-password')
    }


    stages{
        stage("build Docker image using python"){
            steps{
                script{
                    def dockerx = new org.iti.docker()
                    dockerx.build("python", "${BUILD_NUMBER}")
                }
               
            }
        }
        stage("push Docker image using python") {
            steps {
                withCredentials([
                    usernamePassword(credentialsId: 'dockerhub-user', usernameVariable: 'DOCKER_USER', passwordVariable: 'DOCKER_PASS')
                ]) {
                    script {
                        def dockerx = new org.iti.docker()
                        dockerx.login(env.DOCKER_USER, env.DOCKER_PASS)
                        dockerx.push(env.DOCKER_USER, env.DOCKER_PASS)
                    }
                }
            }
        }
    }
}