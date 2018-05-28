#!groovy

node {
   // Mark the code checkout 'stage'....
   stage 'Checkout'

   // Checkout code from repository
   checkout scm

   // Mark the code build 'stage'....
   stage 'Build'
   // Run the maven build
   sh "./gradlew build"

   stage 'archive'

   archiveArtifacts allowEmptyArchive: false, artifacts: 'build/libs/*.jar'
   junit allowEmptyResults: true, keepLongStdio: true, testResults: "build/test-results/test/*/xml"
}
