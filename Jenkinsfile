pipeline {
    parameters {
        string(name: 'BUILD_ENV', defaultValue: 'development', description: 'Environment to build for')
        choice(name: 'BUILD_OPTION', choices: ['Full', 'Quick'], description: 'Type of build to perform')
    }

    agent any

    stages {
        stage('Plan phase') {
            steps {
                echo "Hello Albina Here - Building for ${params.BUILD_ENV} environment"
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
                echo "Integration test passed for ${params.BUILD_OPTION} build"
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
