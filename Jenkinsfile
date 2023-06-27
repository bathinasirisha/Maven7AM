pipeline 
{
  agent any
  stages {
          stage('delete old repo') 
               {
                 steps {
                        sh 'rm -rf siri'
                        sh 'ls -la'
                        }
               }
    
           stage('clone')
               {
                steps {
                      sh 'git clone https://github.com/bathinasirisha/Maven7AM.git'
                      sh 'ls -la'
                      }
               }
            stage('excute maven') {
                  steps {
                        sh 'mvn clean'
                       }
               }
           

   stage('SonarQube analysis') {
        steps{
        withSonarQubeEnv('sonarqube-9.9.1') { 
        sh "mvn sonar:sonar"
        }
      }
    }
  }
}
