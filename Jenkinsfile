node{

   def tomcatWeb = '/opt/tomcat/webapps'
   def tomcatBin = '/opt/tomcat/bin'
   def tomcatStatus = ''
   stage('SCM Checkout'){
     git 'https://github.com/Sanjana938/pipeline.git'
   }
   stage('Compile-Package-create-war-file'){
      // Get maven home path
      def mvnHome =  tool name: 'Maven', type: 'maven'   
      sh "${mvnHome}/user/bin/maven package"
      }

   stage('Deploy to Tomcat'){
     sh "copy target\\JenkinsPipeline.war \"${tomcatWeb}\\JenkinsPipeline.war\""
   }
      stage ('Start Tomcat Server') {
         sleep(time:5,unit:"SECONDS") 
        sh "${tomcatBin}\\startup.bat"
         sleep(time:100,unit:"SECONDS")
   }
}
