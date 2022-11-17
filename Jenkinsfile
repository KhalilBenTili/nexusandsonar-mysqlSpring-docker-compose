pipeline {
  
  agent any

  stages {

 stage('down docker compose') {
      steps {
         sh 'docker-compose -f docker-composeSX.yml down '
         sh 'docker-compose -f docker-compose.yml down '
      
      }
    }

    stage('docker-compose nexus up') {
      steps {
         sh 'docker-compose -f docker-composeSX.yml up -d --remove-orphans'
      
      }
    }

    stage('docker-compose Spring up') {
      steps {
         sh 'docker-compose -f docker-compose.yml up -d --remove-orphans'
      
      }
    }    
    
    stage('show containers ') {
      steps {
         sh 'docker ps'
      
      }
    } 
    stage('grafana prometheus ') {
      steps {
         sh 'docker restart prometheus'
         sh 'docker restart grafana'
      
      }
    } 



}
 
}
