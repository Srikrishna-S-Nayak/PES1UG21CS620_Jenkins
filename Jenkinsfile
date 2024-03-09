pipeline{
    agent any
    stages{
      stage('Cloning Repo'){
        steps{
          checkout([$class: 'GitSCM',
          branches: [[name: '*/main']],
          userRemoteConfigs: [[url: 'https://github.com/Srikrishna-S-Nayak/PES1UG21CS620_Jenkins/']]])
        }
      }
  
      stage('Build') {
          steps {
            build 'PES1UG21CS620-1'    
            sh 'g++ ./main/test.cpp -o PES1UG21CS620-1'
          }
      }
          
      stage('Test') {
          steps {
            sh './PES1UG21CS620-1'
        }
    }
        
      stage('Deploy') {
          steps {
              echo 'Deploying'
          }
      }
    }

    post {
        failure {
            echo 'Pipeline failed'
        }
    }
}
