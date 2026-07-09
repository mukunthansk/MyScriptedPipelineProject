node {

    stage('Checkout') {
        echo 'Checking out source code...'
        checkout scm
    }

    stage('Compile') {
        echo 'Compiling Project...'
        bat 'mvn clean compile'
    }

    stage('Test') {
        echo 'Running Tests...'
        bat 'mvn test'
    }

    stage('Package') {
        echo 'Packaging Project...'
        bat 'mvn clean package'
    }

    stage('Deploy to Nexus') {
        echo 'Deploying to Nexus...'
        bat 'mvn deploy -s C:\\MyScriptedPipelineProject\\settings.xml'
    }

    stage('Success') {
        echo 'Deployment to Nexus Repository Successful.'
    }
}