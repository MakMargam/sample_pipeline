
node {
    checkout scm
    def customImage = docker.build("my-image:${env.BUILD_ID}")
    docker.withRegistry('https://hub.docker.com') {  
        customImage.push()

    }
    customImage.inside {
        sh 'echo hello'
    }
}
