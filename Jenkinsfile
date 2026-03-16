pipeline{
    agent{
        label 'docker'
    }


stages{
    stage("building docker image"){
        steps{
            script{
                sh "docker build -t marwanmw/reactdev -f Dockerfile.dev ."
            }
        }
    }
    stage("running docker image"){
        steps{
            script{
                env.DOCKER_BUILDKIT=1
                sh "docker run -e CI=true marwanmw/reactdev npm run test"
            }
        }
    }
}
}