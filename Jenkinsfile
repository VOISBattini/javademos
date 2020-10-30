pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh 'mvn -f ssgsems/pom.xml -B -DskipTests clean package'
        archiveArtifacts(artifacts: '**/target/*.war', fingerprint: true)
        sh '''mkdir /home/battini/buildoutput/${BUILD_NUMBER}
cp **/target/*.war /home/battini/buildoutput/${BUILD_NUMBER}'''
      }
    }

  }
}