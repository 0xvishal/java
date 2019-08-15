node {
   def sonarUrl = 'sonar.host.url=http://34.234.178.68:9000'
   def mvn = tool (name: 'maven3', type: 'maven') + '/bin/mvn'
   stage('SCM checkout'){
      git 'https://github.com/vishpari/java'
   }
   stage('Compile-Package'){
   def mvnHOME = tool name: 'maven-3', type: 'maven'
   sh "${mvnHOME}/bin/mvn package"
   }
   
    stage('Sonar Publish'){
	   withCredentials([string(credentialsId: 'jenkins', variable: 'f6586cfe841ddc61747ed4b4f9dac457fe62b3c1')]) {
         def sonarToken = "sonar.login=${sonarToken}"
         sh "${mvn} sonar:sonar -D${sonarUrl}  -D${sonarToken}"
	   }
   }

}
