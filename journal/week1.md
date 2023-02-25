# Week 1 — App Containerization
As part of this week i did the following:
For the required homework:
This was to ensure i got the app running on my local environment

as part of the follow along & some debugging, i got the code to work as shown below

I initially wrote Dockerfile for the back-end of the app, after getting it to run initially got this 404 error
![image](https://user-images.githubusercontent.com/54115472/221356901-30325d2e-475e-45fb-b7db-caddc80c513f.png)

but after a little debugging and switching out the environment variables using the command , it successfully ran with the following command

```docker run --rm -p 4567:4567 -it -e FRONTEND_URL='*' -e BACKEND_URL='*' backend-flask```

![image](https://user-images.githubusercontent.com/54115472/221357035-2500be7d-005a-430d-8aab-045380bd4125.png)

Got the front-end working also:
![image](https://user-images.githubusercontent.com/54115472/221358266-7d524438-3e60-4899-9e82-8c78bf3e7295.png)
Checked into the container logs using ```docker logs CONTAINER_ID -f
docker logs backend-flask -f
docker logs $CONTAINER_ID -f```

and shelled into the container using the Gui option(attach shell) on the docker extention in vs-code on gitpod or the ```docker exec CONTAINER_ID -it /bin/bash```

after ensuring both Ensure both apps running via individual container, the next step was to orchastrate multiple containers through docker-compose file
wrote the docker-compose file, with the front-end and back-end as services.
To get it, one can ```#use the gui, right-click the docker-compose file on vs-code and then the compose up option
in this case , docker-compose -f docker-compose.yml up -d --build ```
![image](https://user-images.githubusercontent.com/54115472/221358830-369713d8-1234-49be-a3c8-e77c320fe55e.png)

Mount directories so we can make changes while we code

security focus
installed and run trufflehog checking for secrets
played around to bfg repo cleaner

I wrote and used docker compose to run multiple containers
