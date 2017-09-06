node {
        checkout scm
    /* .. snip .. */
}
pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'source /root/software/env.sh'
                sh 'mvn clean package' 
                archiveArtifacts artifacts: '**/target/*.jar', fingerprint: true 
            }
        }
        stage('quality') {
            steps {
                sh 'mvn sonar:sonar'
                }
            }
    }
}
node {
    echo " build Completed Successfully"
    
    }