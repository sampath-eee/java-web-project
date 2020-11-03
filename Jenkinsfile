pipeline{
    agent any
    stages{
        stage("Build"){
            steps{
                sh 'mvn clean package'
            }
        }
        stage("Deploy"){
            steps{
                deploy adapters: [tomcat7(credentialsId: 'f8c481e7-9d7e-447e-95e3-ad897c6cd028', path: '', 
                url: 'http://ec2-65-0-98-229.ap-south-1.compute.amazonaws.com:8080/')], 
                contextPath: 'javawebapp', war: '**/java-web-project.war'
            }
        }        
    }
}
