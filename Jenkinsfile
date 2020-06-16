podTemplate(containers: [
    containerTemplate(name: 'automation', image: 'docker:19.03.6', command: 'cat', ttyEnabled: true)
  ],
  volumes: [
    hostPathVolume(mountPath: '/var/run/docker.sock', hostPath: '/var/run/docker.sock')
  ]
  ) {
    node(POD_LABEL) {
            stage('Test') {
                container('automation') {
                            sh 'docker run 107126629234.dkr.ecr.ap-southeast-1.amazonaws.com/evermos-automation:latest npm run test'
                } 
            }
            
    }
}