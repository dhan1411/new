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
                          steps{
                               rm -rf *
                               git branch:'Q1-2024' ,url:'https://github.com/Shantanumajan6/project.git'
                               docker run -dp 80:80 --name test httpd
                               rm -rf /usr/local/apache2/htdocs/index.html
                               sh "cp index.html test:/usr/local/apache2/htdocs"
                               }
                 }

          }
}
