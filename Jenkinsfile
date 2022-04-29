pipeline {
  agent any
  stages {
    /* This is a cross app step */
    stage('Step 1: general step') {
      steps {
        sh 'echo Hello General Stage'
      }
    }

    /* These steps will be triggered based on the directory */
    stage('Step 2: app one') {
      when {
        changeset "app-one/**"
      }
      steps {
        sh 'echo app one got some changes'
        sh './app-one/src/script.sh '
      }
    }
    stage('Step 2:  app two') {
      when {
        changeset "app-two/**"
      }
      steps {
        sh 'echo app two got some changes'
        sh './app-two/src/script.sh '
      }
    }
    stage('Step 2: app three') {
      when {
        changeset "app-three/**"
      }
      steps {
        sh 'echo app three got some changes'
        sh './app-three/src/script.sh '
      }
    }
  }
}