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

                # Ensure venv is created
                if [ ! -d "mlip" ]; then
                    python3 -m venv mlip
                fi

                # Install pytest if not installed
                mlip/bin/python -m pip install --upgrade pip
                mlip/bin/python -m pip install pytest numpy pandas scikit-learn

                # Run pytest using venv's Python
                mlip/bin/python -m pytest --maxfail=1 --disable-warnings

                echo 'Pytest completed successfully'
                '''
            }
        }
        stage('Deploy') {
            steps {
                echo 'In this step, we deploy our project'
                echo 'Depending on the context, we may publish the project artifact or upload pickle files'
            }
        }
    }
}
