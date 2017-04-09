pipeline {
  agent any
  stages {
    stage('Upload file to HDFS') {
      steps {
        sh '''#!/bin/bash
/home/bernard/Pentaho/design-tools/data-integration/kitchen.sh -file=/home/bernard/.jenkins/workspace/pentaho/job1.kjb'''
      }
    }
    stage('Aspen Transform') {
      steps {
        sh '''#!/bin/bash
/home/bernard/Pentaho/design-tools/data-integration/kitchen.sh -file=/home/bernard/.jenkins/workspace/pentaho/job2.kjb'''
      }
    }
  }
}