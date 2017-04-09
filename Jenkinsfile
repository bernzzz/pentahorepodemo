pipeline {
  agent any
  stages {
    stage('upload') {
      steps {
        sh '''/home/bernard/Pentaho/design-tools/data-integration/kitchen.sh -file=/home/bernard/.jenkins/workspace/pentaho/job1.kjb
'''
      }
    }
    stage('Transform') {
      steps {
        parallel(
          "job1": {
            echo 'hello world'
            retry(count: 1) {
              sh '''#!/bin/bash
/home/bernard/Pentaho/design-tools/data-integration/kitchen.sh -file=/home/bernard/.jenkins/workspace/pentaho/job1.kjb'''
            }
            
            
          },
          "job2": {
            echo 'hello world'
            sh '/home/bernard/Pentaho/design-tools/data-integration/kitchen.sh -file=/home/bernard/.jenkins/workspace/pentaho/job2.kjb'
            
          },
          "job3": {
            echo 'hi'
            sh '/home/bernard/Pentaho/design-tools/data-integration/kitchen.sh -file=/home/bernard/.jenkins/workspace/pentaho/job3.kjb'
            
          }
        )
      }
    }
    stage('load') {
      steps {
        echo 'i am done'
        sh '/home/bernard/Pentaho/design-tools/data-integration/kitchen.sh -file=/home/bernard/.jenkins/workspace/pentaho/job1.kjb'
      }
    }
  }
}