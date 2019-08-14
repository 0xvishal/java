node {
   stage('SCM checkout'){
      git 'https://github.com/vishpari/java'
   }
   stage('Compile-Package'){
   def mvnHOME = tool name: 'maven-3', type: 'maven'
   sh "${mvnHOME}/bin/mvn package"
   }
}
