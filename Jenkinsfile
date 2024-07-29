pipeline {
    agent any
    
    stages{
        stage ('Build') {
        steps {
            sh 'mvn clean package'
        }
        post {
            success{
                echo "archiving artifacts"
                archiveArtifacts artifacts: '**/target/*.war'
            }
        }
        }
        stage ('Deploy') {
            step {
			deploy adapters: [tomcat9(credentialsId: 'd6de645a-c175-4798-b1e3-7259fff79bf2', path: '', url: 'http://18.61.236.84:8080/')], contextPath: null, war: '**/*.war'
                  }
       }
         }
         }
