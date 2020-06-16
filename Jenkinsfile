podTemplate(containers: [
    containerTemplate(name: 'docker', image: 'docker:19.03.6', command: 'cat', ttyEnabled: true),
    containerTemplate(name: 'automation', image: '107126629234.dkr.ecr.ap-southeast-1.amazonaws.com/evermos-automation:latest', command: 'cat', ttyEnabled: true)
  ],
  volumes: [
    hostPathVolume(mountPath: '/var/run/docker.sock', hostPath: '/var/run/docker.sock')
  ]
  ) {
    node(POD_LABEL) {
            stage('Test') {
                container('automation') {
                            sh 'ls'
                            sh 'wdio run wdio.conf.js'
                } 
            }
            
    }
}