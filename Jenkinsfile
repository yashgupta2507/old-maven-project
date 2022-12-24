pipeline {
agent any
stages {
//  stage('scm checkout')             //download the code, scm: source code management
//  {steps {sh 'git clone https://github.com/prakashk0301/maven-project/' } }       //if no branch defined then it will download the code from default branch"master"

  stage('scm checkout')
  {steps {git branch: 'master', url: 'https://github.com/prakashk0301/maven-project/' }}
 
  stage('execute unit test framework')
  {steps {withMaven(globalMavenSettingsConfig: '--- Use system default settings or file path ---', jdk: 'JAVA_HOME', maven: 'MAVEN_HOME', mavenSettingsConfig: '--- Use system default settings or file path ---') 
{sh 'mvn test'} }}
}
}
