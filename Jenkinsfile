pipeline {
     agent any
     stages {
         stage('scm checkout') {
              steps {
                 deleteDir()
                 sh 'git clone -b master https://github.com/Thilak09/react-nodejs-example.git'
              }
         }
         stage('docker build') {
               steps {
                  sh 'cd /var/lib/jenkins/workspace/task-01/react-nodejs-example' 

                  sh 'docker build -t taskimage /var/lib/jenkins/workspace/task-01/react-nodejs-example'
               }
         }
         stage('deployment') {
              steps {
                   #fgh
                   sh 'docker stop thilakscontainer' 
                 sh 'docker rm thilakscontainer' 
                sh 'docker run -itd --name thilakscontainer -p 8081:80 taskimage'
              }
         }
     }
}

