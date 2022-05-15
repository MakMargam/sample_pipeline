
node {
    checkout scm
    def customImage = docker.build("my-image:${env.BUILD_ID}")
    docker.withRegistry('', 'DCR-personal') {  
        customImage.push()

    }
    customImage.inside {
        sh 'echo hello'
    }
}
