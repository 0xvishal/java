node {
   def sonarUrl = 'sonar.host.url=http://34.234.178.68:9000'
   def mvnHOME = tool name: 'maven-3', type: 'maven'	
   stage('SCM checkout'){
      git 'https://github.com/vishpari/java'
   }
   stage('Compile-Package'){
   
   sh "${mvnHOME}/bin/mvn package"
   }
}
