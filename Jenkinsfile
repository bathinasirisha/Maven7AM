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
                      sh 'git pull https://github.com/bathinasirisha/Maven7AM.git'
                      sh 'ls -la'
                      }
               }
            stage('excute maven') {
                  steps {
                        sh 'mvn clean'
                       }
               }
            stage('Deploy to Nexus') {
            steps {
               sh 'mvn deploy'
            }
        }
            stage('Depoly to tomcat') {
                  steps {
                       sh 'curl -O http://localhost:8081/repository/siri/com/jdevs/CloudGen/4.0/CloudGen-3.0.war'
                       sh 'cp /root/.jenkins/workspace/pipeline_job/CloudGen-3.0.war /opt/tomcat/apache-tomcat-8.5.88/webapps/'
                      }
           }
  }
}
