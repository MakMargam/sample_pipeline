
node {
    checkout scm
    def customImage = docker.build("my-image:${env.BUILD_ID}")
    docker.withRegistry('', 'DCR-personal') {  
        // customImage.push()
        sh "docker push my-image:${env.BUILD_ID}"

    }
    customImage.inside {
        sh 'echo hello'
    }
}
