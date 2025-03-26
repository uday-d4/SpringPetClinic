pipeline {
    agent any

    tools {
        // Install the Maven version configured as "M3" and add it to the path.
        maven "M3"
    }

    stages {
        
         stage('checkout') {
             steps {
                 git branch: "main", url: "https://github.com/uday-d4/SpringPetClinic.git"

             }
         }
        stage('build') {
            steps {
               
                // Run Maven on a Unix agent.
                sh "mvn compile"

                // To run Maven on a Windows agent, use
                // bat "mvn -Dmaven.test.failure.ignore=true clean package"
            }

  
        }
        
        stage('test') {
            steps {
               
                // Run Maven on a Unix agent.
                sh "mvn test"

                // To run Maven on a Windows agent, use
                // bat "mvn -Dmaven.test.failure.ignore=true clean package"
            }

  
        }
        
         stage('package') {
            steps {
               
                // Run Maven on a Unix agent.
                sh "mvn package"

                
            }
        }
        
        
        stage('deploy') {
            steps {
               
                // Run Maven on a Unix agent.
                sh "java -jar /home/coder/.jenkins/workspace/petClinicDeclarativePipeline1/target/*.jar "

                
            }

  
        }
        
    }
}
