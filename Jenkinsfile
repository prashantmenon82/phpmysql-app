node{
    environment 
    {
    registry = "prashantmenon82/ecommdemo"
    registryCredential = 'dockerhub'
    dockerImage = ''
    }

    stage('SCM Checkout')
    {
        git credentialsId: '4cc785e9-441d-4818-a248-2bfb2148004d', url: 'https://github.com/VardhanNS/phpmysql-app.git'
    }
    
    stage('Run Docker Compose File')
    {
        sh 'docker-compose build'
        sh 'docker-compose up -d'
    }
    stage('PUSH image to Docker Hub')
    {
        docker.withRegistry('', 'dockerhub') {
            sh 'docker push prashantmenon82/ecommdemo'
        }
    }
}
