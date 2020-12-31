pipeline {
  agent any
  stages {
    stage('Buzz Build') {
      steps {
        sh 'chmod +x ./jenkins/build.sh'
        sh './jenkins/build.sh > target/result.txt'
        archiveArtifacts(artifacts: 'target/*.txt', fingerprint: true)
      }
    }

    stage('Buzz Test') {
      steps {
        sh 'chmod +x ./jenkins/test-all.sh'
        sh './jenkins/test-all.sh'
      }
    }

  }
}