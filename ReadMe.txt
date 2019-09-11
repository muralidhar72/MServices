Source Code from D:\MuraliCode\Microservices\spring-microservices-master\03.microservices

All Links at https://github.com/in28minutes/spring-microservices/tree/master/03.microservices

===
URLs
Application	URL
Limits Service	http://localhost:8080/limits POST -> http://localhost:8080/actuator/refresh
Spring Cloud Config Server	http://localhost:8888/limits-service/default http://localhost:8888/limits-service/dev
Currency Converter Service - Direct Call	http://localhost:8100/currency-converter/from/USD/to/INR/quantity/10
Currency Converter Service - Feign	http://localhost:8100/currency-converter-feign/from/EUR/to/INR/quantity/10000
Currency Exchange Service	http://localhost:8000/currency-exchange/from/EUR/to/INR http://localhost:8001/currency-exchange/from/USD/to/INR
Eureka	http://localhost:8761/
Zuul - Currency Exchange & Exchange Services	http://localhost:8765/currency-exchange-service/currency-exchange/from/EUR/to/INR 
	http://localhost:8765/currency-conversion-service/currency-converter-feign/from/USD/to/INR/quantity/10
Zipkin	http://localhost:9411/zipkin/
Spring Cloud Bus Refresh	http://localhost:8080/bus/refresh
=====

http://localhost:8100/limits


amqp

====Latest Working Urls -=====
http://localhost:8100/limits
http://localhost:8100/currency-converter-feign/from/EUR/to/INR/quantity/10000
http://localhost:8761/

http://localhost:8100/currency-exchange-service/currency-exchange/from/EUR/to/INR 
http://localhost:8001/currency-converter-feign/from/EUR/to/INR/quantity/10000

http://localhost:8765/currency-exchange/from/EUR/to/INR

docker tag local-image:tagname reponame:tagname
docker push reponame:tagname

docker tag local-image:tagname pmr2791/pmr2798791:<TAG NAME>
docker push  pmr2791/pmr2798791:<TAG NAME>


docker tag murali/netflix-zuul-api-gateway-server:netflix-zuul-api-gateway-server pmr2791/pmr2798791:netflix-zuul-api-gateway-server && 
docker tag  murali/currency-exchange-service:currency-exchange-service  pmr2791/pmr2798791:currency-exchange-service && 
docker tag  murali/currency-conversion-service:currency-conversion-service  pmr2791/pmr2798791:currency-conversion-service && 
docker tag  murali/limits-service:limits-server  pmr2791/pmr2798791:limits-server &&
 docker tag  murali/spring-cloud-config-server:spring_cloud_server  pmr2791/pmr2798791:spring_cloud_server && 
 docker tag  murali/netflix-eureka-naming-server:netflix-eureka-naming-server  pmr2791/pmr2798791:netflix-eureka-naming-server


docker push pmr2791/pmr2798791:currency-exchange-service && docker push pmr2791/pmr2798791:netflix-zuul-api-gateway-server && 
docker push pmr2791/pmr2798791:currency-conversion-service && docker push pmr2791/pmr2798791:limits-server && docker push pmr2791/pmr2798791:spring_cloud_server && docker push pmr2791/pmr2798791:netflix-eureka-naming-server


Works
http://localhost:8001/currency-exchange/from/EUR/to/INR  (WORKS)
http://localhost:8889/limits (ERROR)
http://localhost:8100/currency-converter-feign/from/EUR/to/INR/quantity/1000 -- Timeout
http://localhost:8765/currency-conversion-service/currency-converter-feign/from/USD/to/INR/quantity/10 (Zul call .. Conenction refused(

