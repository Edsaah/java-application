pipeline{
    agent any
    
    tools{
        maven 'Maven'
    }
    stages{
        stage('Git Clone')
        {
            steps{
                git branch: 'main', 'git branch: 'main', credentialsId: 'my-github-credentials', url: 'https://github.com/Edsaah/java-application.git'
            }
        }
        
        stage('Maven Build'){
            steps{
                sh 'mvn clean install'
            }
        }
        
        stage('SonarQube'){
            steps{
                echo "sonar"
            }
        }
    }
}
