pipeline {
  agent any{
      stages{
        stage('SCM Checkout'){
        git 'https://github.com/maheshreddy32825/Maven-War'
      }
        stage('Compile-package'){
        //Get maven home path
        def mvnHome = tool name: 'MAVEN_HOME', type: 'maven'
        bat "mvn clean install -Dbuild.number=${BUILD_NUMBER}"   
      }
        stage('Deploy to Tomcat'){
         steps{
         deploy adapters: [tomcat8(credentialsId: 'tomcat', path: '', url: 'http://localhost:8080')], contextPath: null, war: 'target/*.war' 
         bat "type nul>C:/Users/mamireddy/tools/apache-tomcat-8.5.46/webapps/${BUILD_NUMBER}.txt"     
      }  
    }
   }
  }     
 }

      

  

  


