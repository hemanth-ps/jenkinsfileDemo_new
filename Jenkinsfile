pipeline{
    tools{
        jdk 'myjava'
        maven 'mymaven'
    }
    agent any
    
    stages{
        stage('Clone git repo')
        {
            steps{
                git '${repoName}'
            }
        }
        stage('Compile the code')
        {
            steps{
                sh 'mvn compile'
            }
        }
         stage('Review the code')
        {
            steps{
                sh 'mvn pmd:pmd'
            }
        }
        stage('Testing')
        {
            steps{
               sh 'mvn test'
            }
            post{
                success{
                    junit 'target/surefire-reports/*.xml'
                }
            }
        }
        stage ('Package')
        {
            steps{
                sh 'mvn package'
            }
        }
    }
}
