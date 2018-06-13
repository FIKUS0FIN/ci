pipeline {
  agent any
  stages {
    stage('test_disk') {
      parallel {
        stage('test_disk') {
          steps {
            sh 'bash -x con.sh'
            echo 'some massage'
          }
        }
        stage('some sec step ') {
          steps {
            sh 'df -h'
            echo 'here is df command'
          }
        }
      }
    }
    stage('artifact') {
      steps {
        archiveArtifacts(artifacts: '*', onlyIfSuccessful: true, excludes: 'zip -r some_art.zip .')
      }
    }
  }
}