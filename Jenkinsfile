pipeline {
    agent any
    parameters{
       string(name: 'VERSION', defaultValue: '', description: 'version to deploy on prod')
        choice(name: 'VERSION', choices: ['1.1.0', '1.2.0', '1.3.0], description: '')
        booleanParam(name: 'executeTests', defualtValue: true, description:'')
    }
    stages {

        stage("Build") {
            steps {
                echo 'Building the application...'
            }
        }

        stage("test") {
            when{
                expression{
                    params.executeTests
                }
            }
            steps {
                echo 'testing the application...'
            }
        }

        stage("Deploy") {
            steps {
                echo 'deploying application...'
                echo "deploying version ${params.version}
            }
        }
    }
}
