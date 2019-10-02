node{
  stage('SCM Checkout'){
     git 'https://github.com/maheshreddy32825/Maven-War'
  }
   stage('Compile-package'){
      //Get maven home path
   def mvnHome = tool name: 'MAVEN_HOME', type: 'maven'
     bat "mvn package"
   }
  stage('Deploy to Tomcat'){
  sshagent(['tomcat-admin']) {
    bat 'scp -o StrictHostKeyChecking=no target/*.war mamireddy@10.11.110.186:C:/Users/mamireddy/tools/apache-tomcat-8.5.46/webapps'
   }
  }
}
