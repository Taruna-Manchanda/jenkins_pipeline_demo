pipeline {
    agent any
    stages {
        stage('One') {
            steps {
                echo 'hi , stage 1'
            }
        }
        stage('Two') {
            steps {
                input('hi , do you wantt to proceed')

            }
        }

        stage('Three') {
            parallel {
                stage('unit test') {
                    steps {
                        echo 'running unit test'

                    }
                }
                stage('integration test') {
                    agent {
                        docker {
                            reuseNode false
                            image 'ubuntu'
                        }
                    }
                    steps {
                        echo 'running integration test'

                    }
                }
            }
        }
    }
}
