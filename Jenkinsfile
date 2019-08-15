node {
   stage('SCM checkout'){
      git 'https://github.com/vishpari/java'
   }
   stage('Compile-Package'){
   def mvnHOME = tool name: 'maven-3', type: 'maven'
   sh "${mvnHOME}/bin/mvn package"
   }
  
    stage('SonarQube analysis') {
    def mvnHOME = tool name: 'maven-3', type: 'maven'
    withSonarQubeEnv(credentialsId: 'f6586cfe841ddc61747ed4b4f9dac457fe62b3c1', installationName: 'sonar-6') {
      sh "${mvnHOME}/bin/mvn package"
    }
}
}
