pipeline{
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
            stage('build maven project '){
                steps{
                   sh 'mvn clean package'
                }
            }
           stage('junit test') {
             steps{
                junit 'springboot-maven-course-micro-svc/target/surefire-reports/*.xml'
           }

        }
        stage('code coverage') {
           steps{
              step( [ $class: 'JacocoPublisher' ] ) 
           }
        }    
   }
}
