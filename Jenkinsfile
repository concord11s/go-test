node {
    docker.image('golang:1.15-buster').inside('-u root -v /var/run/docker.sock:/var/run/docker.sock') {
      checkout scm
      sh 'go run g.go'
    } 
}
