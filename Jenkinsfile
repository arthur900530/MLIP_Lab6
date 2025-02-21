pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh '''#!/bin/bash
                echo 'In C or Java, we can compile our program in this step'
                echo 'In Python, we can build our package here or skip this step'
                '''
            }
        }
        stage('Test') {
            steps {
                sh '''#!/bin/bash
                echo 'Test Step: Running pytest with venv'

                # Activate venv (adjust path if needed)
                source mlip/bin/activate  # For Linux/Mac
                # mlip\\Scripts\\activate  # Uncomment for Windows (if using PowerShell)

                # Run pytest
                pytest --maxfail=1 --disable-warnings

                echo 'Pytest completed successfully'
                '''

            }
        }
        stage('Deploy') {
            steps {
                echo 'In this step, we deploy our porject'
                echo 'Depending on the context, we may publish the project artifact or upload pickle files'
            }
        }
    }
}
