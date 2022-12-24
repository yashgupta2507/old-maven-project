pipeline {
agent any
stages {
  stage('scm checkout')             //download the code, scm: source code management
  {steps { sh "git branch: 'master', url: 'https://github.com/prakashk0301/maven-project/'" }}       //if no branch defined then it will download the code from default branch"master"

}
}
