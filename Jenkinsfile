pipeline {
    agent any
    parameters {
        string(name: 'NUMERIC_PARAM', defaultValue: '10', description: 'Enter a numeric parameter')
    }
    stages {
        stage('Clone Repository') {
            steps {
              git branch: 'main', url: 'https://github.com/Badashamit/DevOps-Final1-Project.git'

            }
        }
        stage('Run Script') {
            steps {
                bat "script.bat ${params.NUMERIC_PARAM}"
            }
        }
        stage('Publish HTML Output') {
            steps {
                publishHTML(target: [
                    reportDir: '',
                    reportFiles: 'output.html',
                    reportName: 'Execution Output'
                ])
            }
        }
    }
}
