// Run on 'cabbage' node.
node('cabbage') {
   // Get the maven tool.
   // ** NOTE: This 'maven3' maven tool must be configured
   // **       in the global configuration.           
   def mvnHome = tool 'maven3'

   // Get the jdk tool.
   // ** NOTE: This 'jdk7_80' jdk tool must be configured
   // **       in the global configuration.           
   env.JAVA_HOME = tool 'jdk7_80'

   // Mark the checkout 'stage'....
   stage 'Checkout'
   checkout scm

   // Mark the code build 'stage'....
   stage 'Build'
   // Run the maven build
   sh "${mvnHome}/bin/mvn clean package exec:java"

   // Mark the archive 'stage'....
   stage 'Archive'
   archive 'target/*.html'
}