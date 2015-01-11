# Docker

  sudo docker run --name pickmeapp -p 9000:9000 -v ~/Projects/Personal/PickmeApp:/home/project -i -t sesteva/grunt-project /bin/bash
  
## Proxy

Once inside docker run these commands in the terminal
  
  export http_proxy="http://172.17.42.1:3128/"
  export https_proxy="http://172.17.42.1:3128/"
  npm config set https-proxy http://172.17.42.1:3128 
  git config --global url."https://".insteadOf git://  
  
## Dependencies

  cd /home/project && \
  npm install && \
  bower install --allow-root
  
## Update Gruntfile
  
  connect: {
      options: {
        port: 9000,
        // change this to '0.0.0.0' to access the server from outside
        hostname: 'localhost'
      },
      
Change localhost to 0.0.0.0 and remove task 'open' from 'serve' target since we dont want grunt to opena browser.

## Run

  grunt serve
      
You can access the app in your host's browsers
      
  http://localhost:9000/
