node {
   def sonarUrl = 'sonar.host.url=http://34.234.178.68:9000'
   def mvnHOME = tool name: 'maven-3', type: 'maven'	
   stage('SCM checkout'){
      git 'https://github.com/vishpari/java'
   }
   stage('Compile-Package'){
   
   sh "${mvnHOME}/bin/mvn package"
   }
   
   
   stage('Deploy to Tomcat'){
      sshagent(['tomcat-dev']) {
         sh 'scp -o StrictHostKeyChecking=no target/*.war ubuntu@34.204.2.87:/var/lib/tomcat8/webapps/ROOT/'
      }
   }
   
   
   
}
