pipeline {
  agent none
  stages {
    stage('checkout') {
      steps {
        sh '''#!/bin/bash
gitclone https://github.com/VINEETHAREDDY007/spring-framework-petclinic.git'''
      }
    }

    stage('build') {
      steps {
        sh '''#!/bin/bash
/opt/maven/bin/mvn clean package'''
      }
    }

    stage('deploy') {
      steps {
        sh '''#!/bin/bash
scp /tmp/july.pem petclinc.war ec2-user@172.31.83.37:/tmp/'''
      }
    }

    stage('testing') {
      steps {
        sh '''#!/bin/bash
curl -I http://172.31.83.37/petclinic/'''
      }
    }

  }
}