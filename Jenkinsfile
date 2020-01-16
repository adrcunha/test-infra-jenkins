pipeline {
  agent {
    docker {
      image 'knative-tests/test-infra/prow-tests:stable'
#      registryUrl 'https://gcr.io/knative-tests/test-infra'
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
