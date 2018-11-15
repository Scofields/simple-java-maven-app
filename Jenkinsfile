pipeline {
    agent none
    stages {
        stage('Build') {
            agent {
                docker {
                    image 'maven:3-alpine'
                    args '-v /root/.m2:/root/.m2' 
                }
            }
            steps {
                sh 'mvn -B -DskipTests clean package'
            }
        }
        stage('BuildImage') { 
            agent {
                docker {
                    image 'ubuntu' 
                }
            }
            steps {
                sh 'echo "this is build images steps"' 
            }
        }
    }
}
