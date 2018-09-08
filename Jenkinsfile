node {
   stage 'Checkout'
   
   
   try {
    stage 'Build'
    sh "${Maven_Home}/bin/mvn clean install"
   
    stage 'Archive'
    archiveArtifacts  'target/petclinic.war'
   } catch (err) {
    emailext body: 'Hi, your build successfully failed', subject: 'Test jenkins', to: 'test@gmail.com'
   }
}
