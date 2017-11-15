# Description
This application part of a school project that I am working on. It is used for inserting **mock data** into a MongoDB Atlas database that I have. Real time insertion of data through this application will be displayed in the [Augmented Reality application](https://github.com/Xdecosee/ar-project) that I worked on.

# Demo

Click [here](https://projectadmin.glitch.me) to view the application!

# Background
My school project aims to research and develop an application to visualize the interactions between computer machines through Augmented Reality(AR) during an Attack and Defense Challenge. During the challenge, each individual will be assigned to a computer and all of them will split into two different teams (Red & Blue). Red Team plays the offense and conduct attacks against the Blue team. On the other hand, the Blue Team members will defend against any incoming attacks. 

I am tasked to develop an application that allow users(spectators/contestants) to see the actions (attack/defense) conducted by each team through AR and 3D modelling. Each computer machine will have a physical AR Marker for machine identification. Users will load the AR application onto their phones and move around the room/lab where the Challenge is held. When an AR marker(barcode marker)is within the phone camera view, the application will check for the machine's identity based on the barcode value of the marker. After identifying the machine, the application will display out Real-Time actions that are conducted by/ targeted towards the machine. 

Click [here](https://projectar.glitch.me) to view the AR application! Read on how to use the AR interface over [here](https://github.com/Xdecosee/ar-project). 

# Purpose of Repository
The AR application mentioned in _Background_ will require Real-Time data. For my project presentation, I will need to show that real-time data can be displayed out in the AR application. Hence, upon loading _index.html_ in this repository, the web page will insert Real-Time data (representing different actions) into my MongoDB Atlas database. From there, the AR application will pull the data and display it out in real-time.   

# How It Works

I came up with a list of integers to represent each type of action. Below is the classification of the actions.

**Note:** I was only given a list of the types of attacks that contestants have performed in the past years of the challenge. Hence for the defending actions, I decided to just call them as defense1, defense2 and defense3.

| Attack Type    | Int    | 
| --------|---------|
| Normal  | 1 |
| Reconnaissance | 2 |
| SQL Injection | 3 |
| Semantic URL Attack | 4 |
| Command Injection | 5 |
| Remote Code Execution | 6 |
| URL Manipulation | 7 |
| Privilege Escalation | 8 |
| Directory Traversal Attack | 9 |

<br/>

| Defense Type    | Int    | 
| --------|---------|
| defense1 | 10 |
| defense2 | 11 |
| defense3 | 12 |


Each mock data inserted to the database will contain the action name and ip addresses which represents the source and destination of the action. The AR application mentioned above is only limited to detect only two markers. Hence, the ip addresses used in this application are only "192.168.180.20" (representing Red Team's machine) and "192.168.110.50" (representing Blue Team's machine). 


Upon loading _index.html_, `randAction()` will be called every 1500ms to perform a random selection of any integer above and insert it into the database  along with ip addresses that represent the machine that initiates the action and the machine that the action is targeted at.

# Resources
* [MongoDB Stitch](https://www.mongodb.com/cloud/stitch)



