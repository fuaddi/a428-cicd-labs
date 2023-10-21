node {
    // Alur kerja akan dieksekusi pada agen Jenkins

    // Tahap 'Build'
    stage('Build') {
        // Tahap ini akan menggunakan Docker untuk menjalankan langkah-langkah build
        docker.image('node:16-buster-slim').inside("-p 3000:3000") {
            sh 'npm install'
        }
    }

    // Tahap 'Test'
    stage('Test') {
        // Tahap ini juga akan menggunakan Docker untuk menjalankan langkah tes
        docker.image('node:16-buster-slim').inside("-p 3000:3000") {
            sh './jenkins/scripts/test.sh'
        }
    }
}

