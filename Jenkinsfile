pipeline {
    agent {
        docker {
            image 'maven:3-alpine' 
            args '-v /root/.m2:/root/.m2' 
        }
    }
    stages {
        stage('Build') {
            environment {
                 HTTPS_PROXY = 'http://PITC-Zscaler-Global-ZEN.proxy.corporate.ge.com:80'
                 HTTP_PROXY = 'http://PITC-Zscaler-Global-ZEN.proxy.corporate.ge.com:80'
                 PROXY_ENABLED = 'TRUE'
            } 
            steps {
                sh 'mvn -e -X -B -DskipTests clean package' 
            }
        }
    }
}
