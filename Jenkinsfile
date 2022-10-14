pipeline{
  agent any  
    }
    stages{
        stage('git stage'){
            steps{
                git branch: 'main', url: 'https://github.com/cnanye007/springboot-maven-nexus-deploy.git'
            }
        }
        stage('build maven project '){
            steps{
               sh 'mvn clean package'
            }
        }
    }
}
