
Download Oracle:-

    - oracle-xe-11.2.0-1.0.x86_64.rpm.zip
    - Download Oracle Database 11g Release 2 Express Edition for Linux x64
    - from http://www.oracle.com/technetwork/database/database-technologies/express-edition/downloads/index.html

downloaded oracle  put into the docker directory

Step 1: copy docker directory to your project root directory:-
        
        - cp docker /var/www/project_directory
      
Step2:you should build docker image :-

        - docker build -t oracle-11g.2 .
    
        here :
             t              =  Name and optionally a tag in the 'name:tag' format
             oracle-11g.2   =  docker image name  
             
step3: view docker images in your system :-

        - docker images
step4:  now run your specific docker image with http port:-

        - docker run --name c1c5c8483664 --shm-size=1g -p 1521:1521 -p 8080:8080 -e 123456 oracle/database:11g.2
        
        here :
              bd9efe486cab : actually you should define you conatiner name.
              --shm-size=1g: shared memory. at least need to 1g ram for run your application in docker
              -p 1521:1521 : oracle database port 
              8080:8080    : host port
              123456       : you should be set your db password
              oracle/database:g.2 : image name which image actually run in your container.

step5: finally start your docker container:-

            - docker start conatiner_name or container id
            
Usages:-

    username : SYSTEM/SYS
    password : 123456
    
    http://127.0.0.1:8080/apex
    
