
node {
   def mvnHome
   stage('checkout_sourcecode') {
      git 'https://github.com/sduddu/Test_Repository.git'
      mvnHome = tool 'MAVEN_HOME'
   }
   stage('build_artifact') {
      
      withEnv(["MVN_HOME=$mvnHome"]) {
         if (isUnix()) {
            sh '"$MVN_HOME/bin/mvn"  clean package'
         } else {
            bat(/"%MVN_HOME%\bin\mvn"  clean package/)
         }
      }
   }

}
