pipeline {
    agent any 
    stages {
      
        stage("clone code") {
            steps {
                script {
                    // Let's clone the source
                    git branch: 'main', credentialsId: 'github', url: 'https://github.com/swethark451/Flask_pipeline'
                }
            }
        }
        stage("build") {
            steps { 
                sh "docker build -t flask . "
            }
        }
        
        stage("deploy") {
          steps{
            sh "docker-compose down && docker-compose up -d "
          }
        }
      
    }
}

    


