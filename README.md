# PennCloud
PennCloud a fully distributed, scalable and fault-tolerant Clone of Google Drive built in C++.

The PennCloud system is designed to provide a robust and scalable cloud service, utilizing a distributed design for enhanced performance
and isolation. Key components include Front-end Servers, Front-end Load Balancer, Backend KV Stores, Backend Master/Load Balancer,
Email Servers, and an Admin Console, all interconnected using gRPC for efficient, language-agnostic communication.

## Code
Due to course policies I cannot openly publish the source code, however if you're interested in the implementation please contact me directly and I can share the code with you.

## Key Features
The key features which our cloud service provides are as follows:
1. User Signup/Login Provides the interface for new users to signup and existing users to login. Login authentication is implemented here.
2. Drive Storage:
   - A web storage service that is a Google Drive miniclone, with functionality for uploading, downloading, moving, deleting and renaming files as well as folders.
   - Our implementation supports nested folder structures, files well above 50 MB in both binary and text formats, as well as the ability to rename nested files and folders.
4. Front-end Load Balancer Balances the load and appropriately routes the requests from clients that connect to the systemto any of the 4 frontend servers. It directs the incoming requests to the Front End Server + Controller.
5. Front-end Server + Controller This node contains all the https endpoints that the client can call (e.g. GET /login, GET /home, POST /data. . . ), as well as the controller logic of how to handle these requests.
4. Backend-end Master/Load Balancer Acts as a load balancer for the KV stores, and provides an interface to access the status of the KV nodes from the frontend/admin console.
5. Key-Value Store Stores and returns data in key-value format similar to Google Bigtable(Chang et al., 2008).

## Architecture
<img width="1003" alt="image" src="https://github.com/user-attachments/assets/8f1a44f2-b671-47b9-8353-8c22b03a9059">

## Full Report:
For more details check out the full report [here](files/PennCLoud_Report.pdf)
