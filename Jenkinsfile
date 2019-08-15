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
    withSonarQubeEnv('sonar-6') {
      sh "${mvnHOME}/bin/mvn sonar:sonar"
    }
}
}
