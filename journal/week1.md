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


I wrote Dockerfiles for the front-end and back-end of the a
Ensure we get the apps running via individual container
Create a docker-compose file
Ensure we can orchestrate multiple containers to run side by side
Mount directories so we can make changes while we code

security focus
installed and run trufflehog checking for secrets
played around to bfg repo cleaner

I wrote and used docker compose to run multiple containers
