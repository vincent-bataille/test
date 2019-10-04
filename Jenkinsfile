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
    stage('deploy') {
      steps {
        echo "deploying..."
    }}
  }
}
