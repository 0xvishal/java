node {
   def sonarUrl = 'sonar.host.url=http://34.234.178.68:9000'
   def mvnHOME = tool name: 'maven-3', type: 'maven'	
   stage('SCM checkout'){
      git 'https://github.com/vishpari/java'
   }
   stage('Compile-Package'){
   
   sh "${mvnHOME}/bin/mvn package"
   }
   stage('SonarQube analysis') {
     withSonarQubeEnv(credentialsId: 'e6403fa307f62b4e1d5dcfabf374029d1d9fd5ed', installationName: 'http://34.234.178.68:9000') {
      sh '${mvnHOME}/bin/mvn org.sonarsource.scanner.maven:sonar-maven-plugin:3.6.0.1398:sonar'
    }
  }	   

}
