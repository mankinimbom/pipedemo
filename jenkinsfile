node('built-in') {
    stage('CheckOut') {
        git 'https://github.com/mankinimbom/maven.git'
    }
    stage('Build') {
       sh 'mvn package'
    }
    stage('Test') {
        git 'https://github.com/mankinimbom/testingproject.git'
        sh 'java -jar /var/lib/jenkins/workspace/project/testing.jar'
    }
    stage('Deploy') {
        deploy adapters: [tomcat9(credentialsId: '13966e2a-4cd8-4d21-a693-4b51ad25fed4', path: '', url: 'http://172.22.121.140:8980/')], contextPath: 'demoapp', war: '**/*.war'
    }
    stage('Delivery') {
        echo 'delivery stage pending configuration'
    }

}
