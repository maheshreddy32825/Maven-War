node{
  stage('SCM Checkout'){
     git 'https://github.com/maheshreddy32825/Maven-War'
  }
   stage('Compile-package'){
      //Get maven home path
   def mvnHome = tool name: 'MAVEN_HOME', type: 'maven'
     bat "mvn clean install -Dbuild.number=${BUILD_NUMBER}"
     bat label: '', script: 'type nul >C:/Users/mamireddy/tools/apache-tomcat-8.5.46/webapps/war-0.0.1/META-INF/${BUILD_NUMBER}.txt'
   }
  stage('Deploy to Tomcat'){
  deploy adapters: [tomcat8(credentialsId: 'admin', path: '', url: 'http://localhost:8080')], contextPath: null, war: 'target/*.war'
  }
}
