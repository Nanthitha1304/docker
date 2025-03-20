pipeline {
    agent any

    stages {
        stage('SCM') {
            steps {
        git branch: 'master', url: 'https://github.com/Nanthitha1304/docker'
            }
        }
        stage('build') {
            steps {
               sh "mvn clean"
               sh "mvn install"
}
}
stage('build to images') {
            steps {
               script{
                  sh 'docker build -t nanthitha13/docker .'
               }
    }
}
stage('push to hub') {
            steps {
               script{
                 withDockerRegistry(credentialsId: 'Docker_cred', url: 'https://index.docker.io/v1/') {
                  sh 'docker push nanthitha13/docker'
               }
            }
            }
}
}
}
