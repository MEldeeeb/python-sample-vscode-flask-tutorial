@Library('libx@main')_

pipeline{
    agent{
        label "bash"
    }
    environment{
        DOCKER_CREDS = credentials('dockerhub-user')
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
        stage("push Docker image using python"){
            steps{
                script{
                    def dockerx = new org.iti.docker()
                    dockerx.login(env.DOCKER_CREDS_USR, env.DOCKER_CREDS_PSW)
                    dockerx.push(env.DOCKER_CREDS_USR, env.DOCKER_CREDS_PSW)

                }
            }
        }
    }
}