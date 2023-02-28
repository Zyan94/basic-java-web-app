
pipeline {

  agent any

  tools {
    maven 'jenkins-maven' 
  }

  stages {
  
    stage('SCM Checkout') {
      steps {
      
          git 'https://github.com/Zyan94/basic-java-web-app.git'            
      }
    }
    
    stage('Build') {
      steps {
        sh 'mvn clean package'
        sh 'mv webapp/target/webapp.war webapp/target/user11.war'
      }
    }
    
    stage('Deploy') {
      steps {
        deploy adapters: [tomcat9(credentialsId: 'tomcat-deployer', path: '', url: 'http://18.140.134.132:8181/')], contextPath: null, war: '**/*.war'
      }
    }    
  
  }
    

}


