pipeline{
         agent{
                label "qa"
              }
          tools {
                 git   "Default"
                 docker "hub.docker.com"
                }
          stages{
                 stage(stage1){
                               rm -rf *
                               docker run -dp 80:80 --name test httpd
                               rm -rf /usr/local/apache2/htdocs/index.html
                               sh "cp index.html test:/usr/local/apache2/htdocs"
                }               }
}
