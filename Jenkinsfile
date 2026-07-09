node {

    def mvnHome = tool 'maven'

    stage('Checkout') {
        echo 'Checking out source code...'
        checkout scm
    }

    stage('Compile') {
        bat "\"${mvnHome}\\bin\\mvn.cmd\" clean compile"
    }

    stage('Test') {
        bat "\"${mvnHome}\\bin\\mvn.cmd\" test"
    }

    stage('Package') {
        bat "\"${mvnHome}\\bin\\mvn.cmd\" clean package"
    }

    stage('Deploy to Nexus') {
        bat "\"${mvnHome}\\bin\\mvn.cmd\" deploy -s C:\\Users\\Mukunthan\\.m2\\settings.xml"
    }

    stage('Success') {
        echo 'Deployment Successful'
    }
}
