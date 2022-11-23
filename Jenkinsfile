pipeline {
  agent any
  stages {
    stage('build-app') {
      steps {
        echo 'this is the build job'
        sh 'npm install'
        sleep 4
      }
    }

    stage('test-app') {
      steps {
        echo 'this is the test job'
        sh 'npm test'
        sleep 9
      }
    }

    stage('package-app') {
      steps {
        echo 'this is the third job'
        sh 'npm run package'
        sleep 7
      }
    }

    stage('archive-app') {
      steps {
        archiveArtifacts '**/distribution/*.zip'
      }
    }

  }
  tools {
    nodejs 'nodejs'
  }
  post {
    always {
      echo 'this pipeline has completed...'
    }

  }
}