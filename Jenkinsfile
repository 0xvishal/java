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
	   withCredentials([string(credentialsId: 'jenkins', variable: '2eb06222bb03d10888effb538d6c35a044eccb14')]) {
         def sonarToken = "sonar.login=${sonarToken}"
         sh "${mvn} sonar:sonar -D${sonarUrl}  -D${sonarToken}"
	   }
   }

}
