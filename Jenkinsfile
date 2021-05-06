podTemplate(label: 'veracode-example-builder', // See 1
  containers: [
    containerTemplate(
      name: 'jnlp',
      image: 'jenkinsci/jnlp-slave:3.10-1-alpine',
      args: '${computer.jnlpmac} ${computer.name}'
    ),
    containerTemplate(
      name: 'gradle',
      image: 'gradle:6.7-jdk11',
      command: 'cat',
      ttyEnabled: true
    ),
  ]
)
{
  node ('veracode-example-builder') {

    stage ('gradle version') { // See 4
      git 'git@github.com:asantra1/anir-rest-service.git'
      container('gradle') {
        sh """
            gradle --version
            pwd
            ls -l .
            ls -l /home/jenkins/agent/workspace
            
        """
      }
    }
  }
}
