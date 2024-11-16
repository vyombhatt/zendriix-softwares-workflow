pipeline {
    agent any
    stages {
        stage('Clone Repository') {
            steps {
                // Clone the develop branch into a specific folder
                checkout([
                    $class: 'GitSCM',
                    branches: [[name: '*/develop']],
                    doGenerateSubmoduleConfigurations: false,
                    extensions: [[$class: 'RelativeTargetDirectory', relativeTargetDir: 'git-content-folder']],
                    userRemoteConfigs: [[url: 'https://github.com/vyombhatt/zendriix-softwares-workflow.git']]
                ])
            }
        }
        stage('Confirm Pull') {
            steps {
                echo "Repository content has been pulled to 'git-content-folder'."
                sh 'ls git-content-folder' // List files to verify
            }
        }
    }
}
