pipeline {
  agent {
    docker {
      image 'prow-tests'
      label 'stable'
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
