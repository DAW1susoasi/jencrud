pipeline {
  agent any
  stages {
    stage('copiar') {
      steps {
        sh '''echo "copiando";
        cp -r ./crud /www;
'''
        sh 'ls'
      }
    }
    stage('notificaciones') {
      steps {
        sh 'echo "notificacion a telegram"'
        sh 'curl -X POST -H "Content-Type: application/json" -d "{\"chat_id\": \"6644496010\", \"text\": \"Falló la tarea $JOB_NAME!! $BUILD_NUMBER,  \", \"disable_notification\": false}" https://api.telegram.org/bot6910914256:AAGPbsMpEj2dEexG8GqgQf_peUSZNBN_O8g/sendMessage'
      }
    }
  }
}
