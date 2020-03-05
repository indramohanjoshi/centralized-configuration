# centralized-configuration
Create centralize configuration to load properties configuration dynamically without restarting application server

#Step-1
First build centralized-configuration-service spring boot project.
  This project will load external configuration from configured git repository.
  Once spring boot application is up and running, configuration can be see as JSON to below url
  http://localhost:8888/a-bootiful-client/default
  
#Step-2
Secoond Build centralized-configuration-client spring boot project.
  This project have actuator dependancy which unable to refresh all such bean marked as refreshscopped.
  Hit below command to refresh all those beans which are marked as refreshscopped.
  curl localhost:8080/actuator/refresh -d {} -H "Content-Type: application/json"

#Step-3
Third hit application REST-API to load application property-
http://localhost:9090/message

#Reference
https://spring.io/guides/gs/centralized-configuration/

Note:- Use below command to shoutdown embedded tomcat server
curl -X POST localhost:port/actuator/shutdown
  
  

