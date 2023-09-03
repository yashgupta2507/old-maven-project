pipeline
{
agent any
stages
{
    stage('scm checkout')
    { steps { git branch: 'master', url: 'https://github.com/prakashk0301/maven-project'}}

    stage ('unit test framework')
    {steps { withMaven(globalMavenSettingsConfig: 'c583f974-18c4-482d-925c-c6b3dbb04489', jdk: 'LOCALJDK', maven: 'LOCALMVN', mavenSettingsConfig: 'b4a17510-35d6-427e-ad2d-a0ee2d4b24c5', traceability: true) {
    sh 'mvn test'
} }}

    stage('build the code')
    {steps {withMaven(globalMavenSettingsConfig: 'c583f974-18c4-482d-925c-c6b3dbb04489', jdk: 'LOCALJDK', maven: 'LOCALMVN', mavenSettingsConfig: 'b4a17510-35d6-427e-ad2d-a0ee2d4b24c5', traceability: true) {
    sh 'mvn package'
}}}

    stage('docker image creation')
    {steps { sh 'docker build -t pkw0301/tomcat2023:latest .' }}

//    stage ('deploy to tomcat')
//    {steps { sshagent(['tomcat-ci-cd']) {
//    sh 'scp -o StrictHostKeyChecking=no webapp/target/webapp.war ec2-user@3.120.205.147:/usr/share/tomcat/webapps/'
//} }}
    
}
}
