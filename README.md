# j8ee-with-payara-micro-hello
From https://www.udemy.com/course/java-enterprise-edition-8/learn/lecture/11004954#overview

# Build
mvn clean package && docker build -t org.example/hello-javaee8 .

# RUN

docker rm -f hello-javaee8 || true && docker run -d -p 8080:8080 -p 4848:4848 --name hello-javaee8 org.example/hello-javaee8 



# Maven install Archetype 
https://mvnrepository.com/artifact/com.airhacks/javaee8-essentials-archetype

# Download payara micro(service)
https://www.payara.fish/downloads/payara-platform-community-edition/
Go to Payara Micro 5.2022.1 (JAR)  press the button "Download"
Rename file payara-micro-5.xxxx.x.jar to pm.jar

# Deploy payara micro 
java -jar pm.jar --deploy /home/marven/workspace/hello-javaee8/hello-javaee8/target/hello-javaee8.war --port 8080
