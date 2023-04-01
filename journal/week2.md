# Week 2 — Distributed Tracing

Instrument our backend flask application to use Open Telemetry (OTEL) with
Honeycomb.io as the provider

**Instrumented the Backend  through Honeycomb.io**

Setup Honeycomb and created an environment called crudder
![image](https://user-images.githubusercontent.com/54115472/224478908-8713cbe3-6f6c-4795-8afb-e09f8262217a.png)

After bring up/ running docker-compose, The data was visible on Honetcomb

![image](https://user-images.githubusercontent.com/54115472/224504425-87622ac1-160a-4f6a-b48a-748c4f17b7ea.png)

Instrumentation is working

![image](https://user-images.githubusercontent.com/54115472/224504597-c1c8afcd-0e44-435b-babd-037eb9d2418b.png)

To run queries, Added traces while refering to https://docs.honeycomb.io/getting-data-in/opentelemetry/python/ .

Added span called mock-data to the home activities file
I can see the span as shown below

![image](https://user-images.githubusercontent.com/54115472/224505679-b882cd6d-b55b-435f-a15c-05438af73ef4.png)

 After adding attributes to the span
 
 ![image](https://user-images.githubusercontent.com/54115472/224506961-f395d8f9-cfbb-43d2-91a1-f6bcf8121dcb.png)

**next stage Instrument Xray**
Instrument AWS X-Ray into backend flask application

added the x-ray sdk code
![image](https://user-images.githubusercontent.com/54115472/229285392-311ca251-412d-4b9b-b464-07e7da360b98.png)

added the xray json file for sampling rules

then create an x-ray group
![image](https://user-images.githubusercontent.com/54115472/229286908-745be9b2-8284-4d84-b10c-b19f1fa032a2.png)


Configure and provision X-Ray daemon within docker-compose and send data back to X-Ray API
add into docker-compose.yml
![image](https://user-images.githubusercontent.com/54115472/229299532-536903ed-f43c-48f4-be5d-d92d6f4c8a2c.png)
![image](https://user-images.githubusercontent.com/54115472/229299684-701c172f-e481-41cf-becb-a982d992e437.png)

Observe X-Ray traces within the AWS Console
![image](https://user-images.githubusercontent.com/54115472/229299452-929c53fb-6e98-4bbe-b205-3d83a6cf165e.png)

#CLOUDWATCH LOGS
Install WatchTower and write a custom logger to send application log data to - CloudWatch Log group

add watchtower to requirements.txt

cloudwatch groups os now populated
![image](https://user-images.githubusercontent.com/54115472/229304653-ef066efd-418a-4a9a-a1f8-fde0a8580abe.png)
![image](https://user-images.githubusercontent.com/54115472/229304677-649eca4f-6a79-411e-9bdc-15c32df79467.png)
when we hit the home activities api endpoint:
![image](https://user-images.githubusercontent.com/54115472/229304707-460e0dc5-4935-43cd-ba76-f8ddad8357bf.png)
NB: from a cost standpoint i commented out the cloudwatch code
Integrate Rollbar for Error Logging
Trigger an error an observe an error with Rollbar

