# 2019_16_11_finalsubmission


This is project manager application.

Steps to build and run the application : 

Build spring boot application using below : 

cd SBA-proejctmanager 
mvn clean package

Once build is successful, run command "java -jar project-manager.jar" on target folder to start the application

Launch http://localhost:9090/user to check if service is started. 

Build angular spa using below : 

cd SBA-projectmanagerangular
npm install
npm install node-sass@latest
npm rebuild node-sass
npm run build

Once Build is successful , Copy file from dist\projectmanagerspa to nginx/html folder and start nginx.
Copy below in nginx.conf to run application on port 7000

	server {
        listen       7000;
        server_name  localhost;

        location / {
            root   html;
            index  index.html index.htm;
			try_files $uri $uri/ /index.html;
        }

        error_page   500 502 503 504  /50x.html;
        location = /50x.html {
            root   html;
        }
    }
    
  To launch the application : 
  
  http://localhost:7000
  
  
Launch swagger documentation with http://localhost:9090/swagger-ui.html


