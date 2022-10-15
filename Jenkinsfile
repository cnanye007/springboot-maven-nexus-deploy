pipeline{
    agent any
       tools {
          maven 'maven'
       }
    stages{
       stage ('Github checkout'){ 
         steps { git branch: 'main', credentialsId: 'Jenkins_github_access_token', url: 'https://github.com/cnanye007/springboot-maven-nexus-deploy.git'
        }      
    }
        stage('Mavenbuild'){
           steps{ 
           sh 'mvn clean install'
        }
     }
        stage('junit test') {
           steps{
               junit (allowEmptyResults: true, skipPublishingChecks: true, testResults: 'target/surefire-reports/*.xml')
          }
        }
        stage('code coverage') {
           steps{
              step( [ $class: 'JacocoPublisher' ] ) 
           }
        }   
   }
}
/*pipeline{
    tools { 
        maven 'maven'    
    }
    agent {
        label 'master'
        }
        stages{
            stage('git stage'){
                steps{
                    git branch: 'main', url: 'https://github.com/cloudtechmasters/springboot-maven-course-micro-svc.git'
                }
            }
            stage('build maven project'){
                steps{
                   sh 'mvn clean install'
                }
            }
           //stage('junit test') {
             //steps{
             //   junit 'springboot-maven-course-micro-svc/target/surefire-reports/*.xml'
           //}

        //}
        stage('junit test') {
           steps{
               junit (allowEmptyResults: true, skipPublishingChecks: true, testResults: 'target/surefire-reports/*.xml')
          }
        }    
        stage('code coverage') {
           steps{
              step( [ $class: 'JacocoPublisher' ] ) 
           }
        }    
   }
}*/

