node {

   stage('Clone Repository') {
        // Get some code from a GitHub repository
        git 'https://github.com/FBHKHAN/discovery-server.git'

   }
   stage('Build') {
        docker.build("discovery-server-build")
    }

   stage('Deploy') {

        //Remove maven-build-container if it exists
        //sh "docker rm -f maven-build-container"

        //Run application image
        sh "docker run --name discovery-server -p 8760:8761 discovery-server-build"
   }

}