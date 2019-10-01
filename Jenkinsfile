node{
  stage('SCM Checkout'){
     git 'https://github.com/maheshreddy32825/Maven-War'
  }
   stage('Compile-package'){
      //Get maven home path
   def mvnHome = tool name: 'MAVEN_HOME', type: 'maven'
     sh "$(mvnHome}/bin/mvn package"
   }
}
