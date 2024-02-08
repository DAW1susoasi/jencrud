pipeline {
  agent any
  stages {
    stage('copiar') {
      steps {
        sh '''echo "copiando";
        cp -r ./crud /www;'''
        sh 'ls'
      }
    }
  }
  post {
    success {
      // sh 'curl -X POST -H "Content-Type: application/json" -d "{\\"chat_id\\": \\"6644496010\\", \\"text\\": \\"Tarea $JOB_NAME OK!! $BUILD_NUMBER,  \\", \\"disable_notification\\": false}" https://api.telegram.org/bot6910914256:AAGPbsMpEj2dEexG8GqgQf_peUSZNBN_O8g/sendMessage'
      // emailext(subject: 'Jenkins', body: 'Tarea OK', attachLog: true, to: 'papi@marchantemeco.duckdns.org')
       sh 'mail -s "Tarea OK" papi@marchantemeco.duckdns.org'
    }
    failure {
      // sh 'curl -X POST -H "Content-Type: application/json" -d "{\\"chat_id\\": \\"6644496010\\", \\"text\\": \\"Falló la tarea $JOB_NAME!! $BUILD_NUMBER,  \\", \\"disable_notification\\": false}" https://api.telegram.org/bot6910914256:AAGPbsMpEj2dEexG8GqgQf_peUSZNBN_O8g/sendMessage'
      // emailext(subject: 'Jenkins', body: 'Tarea fallida', attachLog: true, to: 'papi@marchantemeco.duckdns.org')
       sh 'mail -s "Tarea fallida" papi@marchantemeco.duckdns.org'
    }
  }
}
