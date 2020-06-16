podTemplate(containers: [
    containerTemplate(name: 'automation', image: '107126629234.dkr.ecr.ap-southeast-1.amazonaws.com/evermos-automation:latest', command: 'cat', ttyEnabled: true)
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