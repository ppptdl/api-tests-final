pipeline {
    agent any
    // how often Jenkins will check for changes in github
    triggers{
        //check for code changes every minute
        pollSCM('*/1 * * * *')
    }

    stages {
        stage('build-and-push') {
            steps {
                build_image()
                push_image()
            }
        }
    }
}

def build_image(){
    echo "Building docker image"
    sh "docker build -t peterispp/api-tests:latest ."

    echo "Method build_image completed"
}

def push_image(){
    echo "Pushing image to docker registry"
    sh "docker push peterispp/api-tests:latest"

    echo "Method push_image completed"
}