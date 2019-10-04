pipeline {
  agent any
  stages {
    stage('init') {
      steps {
        echo "testing..."
    }}
    stage('build') {
      steps {
        bat 'mvn clean package'
      }
      post {
        success {
          echo 'now archiving...'
          archiveArtifacts artifacts: '**/target/*.war'
        }
      }
    }
    stage('package') {
      steps {
        build job: 'package'
    }}
    stage('deploy to test') {
      steps {
        build job: 'deploy-test'
    }}
  }
}
