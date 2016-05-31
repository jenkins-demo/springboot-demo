docker.image('cloudbees/java-build-tools:0.0.7.1').inside {

   // Mark the code checkout 'stage'....
   stage 'Checkout'

   // Get some code from a GitHub repository
   checkout scm

   // Mark the code build 'stage'....
   stage 'Build'
   // Run the gradle build
   sh "${pwd()}/gradlew build"

   stage 'Report'
   step([$class: 'JUnitResultArchiver', testResults: '**/build/test-results/*.xml'])
}
