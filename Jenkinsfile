pipeline {
    agent { label 'jenkins-agent' }
    tools {
        jdk 'java17'
        maven 'maven3'
    }
    stages{
        stage("Cleanup Workspace"){
                steps {
                cleanWs()
                }
        }

        stage("Checkout from SCM"){
                steps {
                    git branch: 'main', credentialsId: 'github', url: 'https://github.com/suhas25-git/register-app'
                }
        }

        stage("Build Application"){
            steps {
                sh "mvn clean package"
            }

       }

       stage("Test Application"){
           steps {
                 sh "mvn test"
           }
       }
       //  stage("SonarQube Analysis"){
       //     steps {
	      //      script {
		     //    withSonarQubeEnv(credentialsId: 'jenkin-sonarqube-tokan') { 
       //                  sh "mvn sonar:sonar"
		     //    }
	      //      }	
       //     }
       // }
}
}
