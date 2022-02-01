pipeline{
    agent any
    
    tools{
        maven 'Maven'
    }
    stages{
        stage('Git Clone')
        {
            steps{
                git branch: 'main', credentialsId: 'my-github-credentials', url: 'https://github.com/Edsaah/java-application.git'
            }
        }
        
        stage('Maven Build'){
            steps{
                sh 'mvn clean install'
            }
        }
        
        stage('SonarQube'){
            environment{
                    scannerHome = tool 'Sonar'
                }
            steps{
                withSonarQubeEnv('SonarServer'){
                    sh "${scannerHome}/bin/sonar-scanner -Dsonar.projectKey=Java_Application -Dsonar.sources=. -Dsonar.java.binaries=target/classes/com/mycompany/app/"
                }
                
            }
        }
    }
}
