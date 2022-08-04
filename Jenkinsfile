node('ec2') {
   // Mark the code checkout 'stage'....
   stage ('Checkout'){

      // Get some code from a GitHub repository
      checkout scm
      
   }

   def mvnHome = tool 'maven3'
   // Mark the code build 'stage'....
   stage ('Build Maven'){
      // Get the maven tool.
      // ** NOTE: This 'maven3' maven tool must be configured
      // **       in the global configuration.

      // Run the maven build
      sh "${mvnHome}/bin/mvn clean compile"
   }
   
   stage('Test') {
      sh "${mvnHome}/bin/mvn test"
   }
}
