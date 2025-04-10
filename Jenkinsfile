pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Ambil source code dari repo Git (jika kamu pakai Git)
                checkout scm
            }
        }

        stage('Build') {
            steps {
                echo 'Build stage: kamu bisa tambahkan proses build di sini jika perlu'
            }
        }

        stage('Publish HTML') {
            steps {
                echo 'Mengarsipkan file index.html dan CSS...'
                archiveArtifacts artifacts: '**/*.html, **/*.css', fingerprint: true
            }
        }
    }

    post {
        success {
            echo 'Build berhasil! Kamu bisa buka file HTML via tab "Artifacts".'
        }
        failure {
            echo 'Build gagal.'
        }
    }
}
