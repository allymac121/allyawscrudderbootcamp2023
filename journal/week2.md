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

Run queries to explore traces within Honeycomb.io
Instrument AWS X-Ray into backend flask application
Configure and provision X-Ray daemon within docker-compose and send data back to X-Ray API
Observe X-Ray traces within the AWS Console
Integrate Rollbar for Error Logging
Trigger an error an observe an error with Rollbar
Install WatchTower and write a custom logger to send application log data to - CloudWatch Log group
