pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Mengambil kode dari repositori Git
                git 'https://github.com/dyo713/kalkulator-sederhana'
            }
        }
        stage('Build') {
            steps {
                // Langkah untuk membangun aplikasi
                sh 'npm install' // Contoh jika menggunakan npm
                sh 'npm run build' // Contoh jika menggunakan npm
                // Atau perintah build sesuai dengan teknologi yang digunakan
            }
        }
        stage('Test') {
            steps {
                // Langkah untuk menjalankan pengujian
                sh 'npm test' // Contoh jika menggunakan npm
                // Atau perintah pengujian sesuai dengan teknologi yang digunakan
            }
        }
        stage('Deploy') {
            steps {
                // Langkah untuk melakukan deployment
                // Contoh deployment ke server menggunakan SSH
                sshagent(['ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAIGJQstOIhQSuNDbPvN1aw9rURGShWBJMIzfsztViEFYj diopramudya73@gmail.com']) {
                    sh 'git@github.com:dyo713/kalkulator-sederhana.git "cd /path/to/deployment && git pull" ' // Contoh deployment via Git pull
                    // Atau perintah deployment sesuai dengan teknologi yang digunakan
                }
            }
        }
    }

    post {
        always {
            // Langkah yang dijalankan setelah semua tahapan selesai, misalnya membersihkan lingkungan
            cleanWs()
        }
    }
}
