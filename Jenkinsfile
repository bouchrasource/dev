pipeline {
    agent any
         triggers {
              cron 'H/1 * * * * '
            }
    stages {
        stage('checkout') {
            steps{
             git branch: 'main', url: 'https://github.com/xonatis-academy/epsi-dev709-ci.git'
            }  

            }
        
        stage('clean'){
            steps{
                dir ('projects/erphrense'){
               bat './mvnw clean' 
              
    }
                
            }
    }
    stage('compile'){
            steps{
                dir ('projects/erphrense'){
             
               bat './mvnw compile'
               
    }
                
            }
    }
    stage('test'){
            steps{
                dir ('projects/erphrense'){
               
               bat './mvnw test'
               
    }
                
            }
    }
    stage('package'){
            steps{
                dir ('projects/erphrense'){
              
               bat './mvnw package'
              
    }
                
            }
    }
    stage('archive'){
            steps{
                dir ('projects/erphrense'){
              
               bat 'rename target\\erphrense-0.0.1-SNAPSHOT.jar erphrense-%BUILD_NUMBER%.jar'
               archiveArtifacts artifacts: 'target\\erphrense-*.jar', followSymlinks: false
    }
                
            }
    }
    
}
}
