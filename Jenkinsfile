pipeline {
  agent any
  stages {
    stage('upload') {
      steps {
        echo 'uploading'
      }
    }
    stage('Transform') {
      steps {
        parallel(
          "job1": {
            echo 'hello world'
            echo 'fuck you'
            
          },
          "job2": {
            echo 'hello world'
            
          },
          "job3": {
            echo 'hi'
            
          }
        )
      }
    }
    stage('load') {
      steps {
        echo 'i am done'
      }
    }
  }
}