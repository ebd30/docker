# docker

ubuntu os

If Docker is already down:

    $sudo apt-get remove docker docker-engine docer.io containerd runc

docker download: 

  package install: 
  
    $sudo apt-get update
    $sudo apt-get install -y ca-certificates curl gnupg lsb-release apt-transport-https
    
  add gpg key:
  
    $curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
  or
    
    $ curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
    
  check gpg key:
    
    $sudo apt-key fingerprint 

  add docker repository:
  
      $echo \
    "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu \
    $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
  
      If you want a nightly or test channel, change it from above if you want a stable channel.

  update package list:
  
    $sudo apt-get update

  docker CE install:
  
    $sudo apt-get install -y docker-ce docker-ce-cli containerd.io

  Check docker installed: 
    
    $docker version

  test image recognition and container execution are possible:
    
    $sudo docker run test-test 

docker compose install:
  https://docs.docker.com/compose/install(link) <- please refer to the following url
  
  download the command executable file:
    
    $curl -L "https://github.com/docker/compose/releases/download/"version you want"/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose

  check docker compose installed:
    
    $sudo chmod +x /usr/local/bin/docker-compose
    $docker-compose version

  run without sudo:
    
    $sudo usermod -aG "$(id -nu)"

  check:
    
    $id -nG
    $docker version
