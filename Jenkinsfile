pipeline {
  agent any
  stages {
    stage ('install jenkins') {
      steps {
        sh "yum install docker -y"
         sh "systemctl start docker"
        sh "systemctl enable docker"
        sh "docker stop brijal"
         sh "docker system prune -a -f"
      }
    }
    stage ('23Q1') {
      steps {
         sh "cd /mnt/deepika"
       sh "git checkout 23Q1"
        
      
        sh "docker run -itdp 80:80 --name brijal httpd"
        sh "docker cp index.html brijal:/usr/local/apache2/htdocs"
    
        sh "docker exec brijal chmod -R 777 /usr/local/apache2/"
      }
    }
  }
}
