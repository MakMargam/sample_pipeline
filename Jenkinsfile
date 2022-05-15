@Library('global-vars') _
node {
    checkout scm
    def customImage = docker.build("mak2497/my-image:${env.BUILD_ID}")
    docker.withRegistry('', 'DCR-personal') {  
        helloWorld()
        customImage.push()
        // sh "docker push my-image:${env.BUILD_ID}"

    }
    customImage.inside {
        sh 'echo hello'
    }
}
