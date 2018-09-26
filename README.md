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

1) Server :- Server is located remotely and has the ability to accept connection from multiple clients and process their     request. Server is launched on the port provided by the user and accepts connections from clients. Once a client is connected a server will spawn of a new thread for each client connected 
     
   




