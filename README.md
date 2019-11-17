# nodejs
task: Implement Master-Slave Configuration in Jenkins.
      Build a slave server to run NodeJS Applications.
how to: download any sample server.js file with hello world code written for nodejs and push it to github by creating a repo
        then pull it to jenkins slave server through pipeline code of:
CODE: pipeline {
        agent { label 'jen-slv2'}
        stages {
          stage('installing packages and nodejs') {
           steps {
              sh 'sudo apt-get install curl'
              sh 'curl -sL https://deb.nodesource.com/setup_13.x | sudo -E bash -'
              sh 'sudo apt-get install nodejs -y'
              git url: 'https://github.com/vamshiktony/nodejs.git'
              sh 'pwd'
              sh 'ls'
              sh 'node server.js'
              }
           }
         }
  Then run the server using its ip
  output: Hello World
