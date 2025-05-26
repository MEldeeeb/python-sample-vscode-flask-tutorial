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
                // S
            }
        }
        stage("push Docker image using python"){
            steps{
                script{
                    def dockerx = new org.iti.docker()
                    dockerx.login("${DOCKER_USER}", "${DOCKER_PASS}")
                    dockerx.push("${DOCKER_USER}", "${DOCKER_PASS}")
                }
            }
        }
    }
}