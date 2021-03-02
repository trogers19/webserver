From COSC 340 Assignment README.md:

# Learning to use cloud platform

This exercise will involve creating a docker container and running it on the Google Cloud 
platform. 


## Google Cloud Credits To run VMs in the cloud

Here is the URL you will need to access in order to request a Google Cloud Platform coupon. 
You will be asked to provide your school email address and name. 
An email will be sent to you to confirm these details before a coupon is sent to you.


[Student Coupon Retrieval Link](https://google.secure.force.com/GCPEDU?cid=tsA8EfZIOwZZi1%2FfL5I%2BIBjylggBp5dRvmg8Z0Et0dtRqpmB3ivur6R7NOvG3ldT)

You will be asked for a name and email address, which needs to match the domain. A confirmation email will be sent to you with a coupon code.

You can request a coupon from the URL and redeem it until: 5/21/2021

Coupon valid through: 1/21/2022

You can only request ONE code per unique email address.

GCP requires projects to be linked to a billing account. If you plan to use GCP for your project, you might want to redeem all credits on a single account and add other members of the same team to that project. 

Once you get coupon go to:
https://console.cloud.google.com/education

Create a project, e.g.cs340, select it, 
enter coupon code!

Go to compute engine VM Instances

Now you should be able to create an instance!!!!


# Assignment 1: Deploying a webserver 

The purpose of the assignment is to familiarize you with the automatic build, containers, and cloud computing

## The due date is Mar 11.

1. Create repo yougithubid/webserver
2. Add Dockerfile, for example as the one in this repo
3. Add index.html with your name in it
4. Create automatic build

       i. on hub.docker.com create id for yourself (if you have not done so before)
       ii. create automated build (pull out from the top menu)
       iii. connect to github repo you have just created
5. make a change on the github repo (to trigger build)
6. Verify that the build succeeded https://hub.docker.com/r/yourdockerhubid/webserver/builds/
7. Create a virual machine on GCP

       i. go to https://console.cloud.google.com/compute/instances select the class project and click on craete instance
       ii. Next to memory click customize and reduce 1G
       iii. Mark checkmark "Deploy a container image to this VM" and enter image 'yourdockerhubid/webserver'
       iv. Mark checkmark "Allow HTTP traffic"
       v. click Deploy Container checkbox and enter your container image: yourdockerhubid/webserver
       vi. expand "Advanced Container Options"
       vi. in the "Command" box enter    
```    
[ "--name ws", "-p80:80" ]
```
8. Click "Create" button at the bottom
9. Check if the webserver works
       
         i. enter the external ip adress (for the machine you created) in your browser (you should get your name)
         ii. If that does not work connect to the machine
         iii. Open shell (via gcp console)
         iv. once connected to your instance type 'docker ps': your container should be running
10. Enter ip adress of the machine (just the ip, nothing else) as the
    last line of your netid.md file in the cs340-21/students repo and create a pull request
         
