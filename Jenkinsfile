node{
  stage('SCM Checkout'){
     git 'https://github.com/maheshreddy32825/Maven-War'
  }
   stage('Compile-package'){
      //Get maven home path
   def mvnHome = tool name: 'MAVEN_HOME', type: 'maven'
     bat "type nul>C:/Program Files (x86)/Jenkins/workspace/Deploy war/src/main/webapp${BUILD_NUMBER}.txt"
     bat "mvn clean install -Dbuild.number=${BUILD_NUMBER}"   
   }
  stage('Deploy to Tomcat'){
  deploy adapters: [tomcat8(credentialsId: 'admin', path: '', url: 'http://localhost:8080')], contextPath: null, war: 'target/*.war'
   }
}
