node {
     stage('Clone repository') {
         checkout scm
     }
     stage('Build image') {
         app = docker.build("assd5070/flask-example")
     }
     stage('Push image') {
         docker.withRegistry('https://registry.hub.docker.com', 'docker-hub') {
             app.push("${env.BUILD_NUMBER}")
             app.push("latest")
         }
     }
}
