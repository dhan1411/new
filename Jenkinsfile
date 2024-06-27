pipeline{
         agent{
                label "qa"
              }
          tools {
                 git   "Default"
                 dockerTool "docker"
                }
          stages{
                 stage("stage0"){
                          steps{ sh "rm -rf *"
                                 
                                }
                               }

                 stage("stage1"){
                          steps{
                               
                               git branch:'Q1-2024' , url:'https://github.com/dhan1411/new.git'
                               sh "docker stop test"
                               sh "docker rm test"
                               sh "docker run -dp 80:80 --name test httpd"
                               sh "docker exec test rm -rf /usr/local/apache2/htdocs/index.html"
                               sh "docker cp index.html test:/usr/local/apache2/htdocs"
                               }
                               }
                 stage("stage2"){
                          steps{
                               sh "docker stop test1"
                               sh "docker rm test1"
                               git branch:'Q2-204' , url:'https://github.com/dhan1411/new.git'
                               sh "docker run -dp 90:80 --name test1 httpd"
                               sh "docker exec test1 rm -rf /usr/local/apache2/htdocs/index.html"
                               sh "docker cp index.html test1:/usr/local/apache2/htdocs"
                               }
                               }
                 stage("stage3"){
                          steps{
                               sh "docker stop test2"
                               sh "docker rm test2"
                               git branch:'Q3-2024' , url:'https://github.com/dhan1411/new.git'
                               sh "docker run -dp 8080:80 --name test2 httpd"
                               sh "docker exec test2 rm -rf /usr/local/apache2/htdocs/index.html"
                               sh "docker cp index.html test2:/usr/local/apache2/htdocs"
                               }
                               }

                 }

          }
