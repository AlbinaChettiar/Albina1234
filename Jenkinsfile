pipeline {
    agent any

    stages {
        stage('Plan phase') {
            steps {
                echo 'Hello Albina Here'
            }
        }

        stage('Code phase') {
            steps {
                input 'Do you want to continue?'
            }
        }

        stage('Integrate phase') {
            when {
                not {
                    branch 'master'
                }
            }
            steps {
                echo 'Integration test passed'
            }
        }

        stage('Testing phase') {
            parallel {
                stage('Unit test') {
                    steps {
                        echo 'Running unit test'
                    }
                }
            }
        }
    }
}
