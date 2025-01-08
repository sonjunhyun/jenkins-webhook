node {
  stage('Clone repository') {
    git credentialsId: 'github-access-token', url: 'https://github.com/sonjunhyun/jenkins-webhook.git'
  }

  stage('Build image') {
    dockerImage = docker.build("leonica0429/node-front:1.0")
  }

  stage('Push image') {
    withDockerRegistry([ credentialsId: "docker-access", url: "" ]) {
    dockerImage.push()
    }
  }
}
