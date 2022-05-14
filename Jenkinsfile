
node {
    checkout scm
    def customImage = docker.build("my-image:${env.BUILD_ID}")
    docker.withRegistry('https://registry.hub.docker.com', 'DCR-personal') {  
        customImage.push()

    }
    customImage.inside {
        sh 'echo hello'
    }
}
