pipeline {
  agent any
  stages {
    stage('CheckOut') {
      steps {
        parallel(
          "CheckOut": {
            git(url: 'https://github.com/devopsus/demo.git', poll: true, branch: '*', changelog: true)
            
          },
          "PreCheck1": {
            sh 'whoami'
            
          },
          "PreCheck2": {
            sh 'uname -a'
            
          }
        )
      }
    }
    stage('Build') {
      steps {
        parallel(
          "Build": {
            sh 'echo "Building now"'
            
          },
          "Build-PreCheck": {
            sh 'echo "Build PreCheck"'
            
          }
        )
      }
    }
    stage('Test') {
      steps {
        parallel(
          "Test": {
            sh 'echo "Test"'
            
          },
          "Test1": {
            sh 'echo "Test 1"'
            
          },
          "Test2": {
            sh 'echo "Test 2"'
            
          },
          "Test3": {
            sh 'echo "Test 3"'
            
          }
        )
      }
    }
    stage('Package') {
      steps {
        sh 'echo "Packageing now"'
      }
    }
    stage('Harbor') {
      steps {
        echo 'img is stroring'
      }
    }
    stage('Staging') {
      steps {
        echo 'staging now'
      }
    }
    stage('Release') {
      steps {
        echo 'release'
      }
    }
    stage('ReadyGo') {
      steps {
        echo 'ReadyToGo'
      }
    }
  }
}