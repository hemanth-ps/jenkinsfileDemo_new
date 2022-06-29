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
                git 'https://github.com/Sonal0409/DevOpsCodeDemo.git'
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
