# MultithreadedFTP

Distributed Systems (CSCI 6780 ,Spring 2017)

Team Members :- Vibodh Fenani , Shrutika Gamare

Technologies used :- Java 8, Sockets, Java Threads

# Problem Statement

Implement a Client - Server model in which Server can accept multiple clients who can synchronously or concurrently
access, update or delete files

# Commands

get :- (get filename) Eg get abc.txt A client connected can download the file located on remote server.

put :-(put filename) Eg put abc.txt  A client connected can upload the file located on it's local directory to server's local                         directory 

get & :- (get filename &) Eg get abc.txt & . get command followed by & symbol enables client to fire other commands while file gets downloaded from remote server. Additionally this will also generate a command id

put & :- (put filename &) Eg put abc.txt & . put command followed by & symbol enables client to fire other commands while file gets downloaded from remote server

pwd :- Returns the current working directory of server

ls :- lists all files present in current working directory of server

mkdir :- (mkdir temp) creates a folder with specified named on the current working directory of the server

delete :- (delete filename) deletes the file if it is present on the server

terminate :- (terminate commandID) terminates get or put request which is currently ongoing

quit :- the client exits when it fires quit command


# Instructions to run

1) Create a folder and place ServerSide.java inside that folder
    
    Compile - javac ServerSide.java
   
    Run -    java ServerSide
    
2) Create separate folders and place ClientSide.java inside that folder
    
    Compile - javac ServerSide.java
   
     Run -    java ServerSide
     
# Detailed Description   

Multithreaded File Transfer aims in maintaining a distributed Client-Server architecture where in multiple clients
can access the server concurrently or synchronously depending on the request. It makes use of a multithreaded environment
and has two main components

1) Server :- Server is located remotely and has the ability to accept connection from multiple clients and process their     request. Server is launched on the port provided by the user and accepts connections from clients. Once a client is connected a server will spawn of a new thread for each client connected . For every get or put request that a client will ask for
server will generate a command id and return it to the client. If there are many concurrent get or put request for same resource then it will put those reqeusts in the queue and access will be given to a new resource as and the previous client releases the resource. The client whose request is being processed or if it is held in a queue can any time choose to terminate it's request by sending in the request id. In that case the server will remove the request from the queue

2) Client :- Clients can connect to the server using the ipaddress and port number which is provided by the server. Once a client is connected to the server , it can get an existing file from the server , upload a file on the server or delete the file on the server . It can even get the current directory of the server or list all files which are present on the server.
A client can also change the current working directory of the server. When multiple clients try to access same resource which is present on the server they have to wait in the request queue till the resource is released. The client can fire a terminate command if it wants to release an existing resource

     
   




