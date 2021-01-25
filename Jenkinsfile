pipeline {
  agent {
    docker {
      image 'node:15-alpine'
      args '-u root'
    }

  }
  stages {
    stage('Download repository') {
      steps {
        git(url: 'https://github.com/NiclasEgeler/99damage', branch: 'pipeline-testing')
      }
    }

    stage('Debugging') {
      steps {
        sh 'npm i && chmod 777 ci/version_check.sh && sh ci/version_check.sh && npx build && npm publish'
      }
    }

  }
  environment {
    NPM_TOKEN = 'fefed5cd-289f-41f8-8e04-15710c5e47ab'
  }
}