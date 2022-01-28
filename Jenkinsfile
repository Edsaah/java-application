pipeline{
    agent any
    
    stages{
        stage('Git Clone')
        {
            steps{
                git branch: 'main', credentialsId: 'my-github-credentials', url: 'https://github.com/Edsaah/java-application.git'
            }
        }
    }
}
