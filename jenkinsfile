pipeline {
     agent any
        tools {
           maven 'MAVEN_HOME'
        }  
     stages {
          stage ('checkout') {
             steps {
               dir('app') {
                git branch: 'master',
                url: 'https://github.com/akshayaajitkumar-crypto/MAVEN-SL-01-NOV-PROJECT.git'
             }
            }
          }
          stage('Build') {
           steps {
              dir('app') {
               sh 'mvn clean compile'
             }
           }
         }
          stage ('Test') {
            steps {
                 dir('app') {
                    sh 'mvn test'
                }
                  }
          }
          stage ('PAckage') {
            steps {
                dir('app') {
                 sh 'mvn package'
                 }
                  }
          }
          stage('Deploy') {
            steps {
                echo 'Deployment completed successfully.'
            }
          } 
     }
     post {
        success {
          echo 'Deployed successfuly'
        }
        failure {
          echo 'Build Failed '
        }
     }
}
