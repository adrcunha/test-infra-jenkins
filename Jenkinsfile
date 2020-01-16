pipeline {
  agent {
    docker {
      image 'https://gcr.io/knative-tests/prow-tests:stable'
      registryUrl 'https://gcr.io/knative-tests/'
    }
  }
  stages {
    stage('test') {
      steps {
        echo 'hihi'
        sh 'which kubetest'
      }
    }

  }
}
