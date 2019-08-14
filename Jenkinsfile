node {
   stage('SCM checkout'){
      git 'https://github.com/vishpari/java'
   }
   stage('Compile-Package'){
   sh 'mvn package'
   }
}
