pipeline {
    agent any
    triggers { 
        pollSCM('*/1 * * * *') 
    }
    stages {
        stage('build-docker-image') {
            steps {
                build_docker_image()
            }
        }
    }
}

def build_docker_image(){
    echo "Building docker image.."
    sh "docker build --no-cache -t razmadzeb/api-tests:latest ."

    echo "Pushing docker image to docker registry.."
    sh "docker push razmadzeb/api-tests:latest"
}
