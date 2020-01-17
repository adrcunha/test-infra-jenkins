pipeline {
  agent {
    docker {
      image 'gcr.io/knative-tests/test-infra/prow-tests-go112:stable'
      args '--entrypoint=""'
    }
  }
  stages {
    stage('Build tests') {
      steps {
        sh '''
          set -ex
          pwd
          ls -la
          # hack. there must be a better way.
          export SRC="$(pwd)"
          export GOPATH="$(mktemp -d)"
          mkdir -p $GOPATH/src/knative.dev
          cd $GOPATH/src/knative.dev
          cp -ar $SRC test-infra
          # hack for making the script happy, shouldn't be required
          export PULL_BASE_REF=bogus_base_ref
          export PROW_JOB_ID=bogus_job
          #
          cd $GOPATH/src/knative.dev/test-infra
          ./test/presubmit-tests.sh --build-tests
        '''
      }
    }

  }
}
