node {

    def mvnHome = tool name: 'Maven', type: 'maven'

    stage('Check Maven') {
        echo "Maven Home = ${mvnHome}"
        bat "\"${mvnHome}\\bin\\mvn.cmd\" -version"
    }

    stage('Checkout') {
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
        bat "\"${mvnHome}\\bin\\mvn.cmd\" deploy -s settings.xml"
    }
}
