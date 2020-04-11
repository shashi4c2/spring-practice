node('UBUNTU') {
    stage('GIT') {
        git 'https://github.com/shashi4c2/spring-practice.git'
    }
    stage('package') {
        sh 'mvn package'
    }
    stage('archiveartifacts') {
        archive 'target/*.jar'
    }
    stage('archivetestresults') {
        junit 'target/surefire-reports/*.xml'
    }
    stage("deployment') {
        sh 'docker image build -t petclinic /home/jenkins/images/spring-petclinic
        sh 'docker container run -d -p 8081:8080 petclinic
    }
}
