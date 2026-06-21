# MFAR
 
Project description: Imagine you work at a bank that process credit card applications. Everyday thousands of requests flow through a system called the orchestration service. It calls other services runs businesses rules decides whether to approve or decline the credit line increases. 
Now imagine businesses want to add new features : co-owner merge. This let existing card holder add a co-owner to their account. The co-owner needs their own credit check, their own bureau pull, their own risk assessment. 

A key challenge was ensuring that the new "Co-Owner Merge" feature, which allows merging two existing accounts into one, could be safely deployed without risking accidental bureau pulls or incorrect decisions. To achieve this, I implemented robust logic isolation and environment management strategies, allowing us to deploy from a single codebase while maintaining strict control over feature rollout.

You can’t break the existing system while building the new one.The existing system BAU processes real customer requests in production. 
If your co-owner merge code accidentally runs against a regular credit line increase request, bad things happen: wrong decisions extra bureau pull cost money 
So how do you build a new feature alongside an existing system deploy them from sane codebase and guarantee they never interfere with each other. 

Understanding:
   Orchestration services:
    Think orchestration service an assembly line. a request arrives move through the stations and emerge as decision. 
   Request arrives  (should we increase this credit line) 
      - station 1: Account Data: Call AU Microservice- get Account Info
        station 2:  Error Check -runs error rules is this request even valid.?
        Station 3: Burea data: Call CUBE Microservice: get Bureau data.
        Station 4: Decision Rules
        Station 5: Send response, save to database and publish to Kafka. 

The current app is ECS fargate using Splunk Universal Forwarder push pattern (host side log file shipping)  
I have a new application environment (arsqa) writing logs to var/log/arsqa/cdn-verification-service/app.log on ECS host in AWS account. 
 
  I have summarized my recent project work on the banking platform’s orchestration service for our webpage display:

  - Developed an orchestration service for a high-volume banking platform processing thousands of daily credit card applications.
  - Managed an "assembly line" workflow integrating AU service (account data), error validation, CUBE service (bureau data), and final decisioning.
  - Implemented the "Co-Owner Merge" feature, enabling independent credit checks and risk assessments separate from BAU credit line increase requests.
  - Ensured safe deployment via logic isolation and environment management to prevent accidental bureau pulls or incorrect decisions from a single codebase.
  - Integrated automated data publishing to Kafka and internal databases for downstream processing.

Professional summary of a recent project I worked on, specifically framed for an upcoming interview.

In this project, I worked on an orchestration service for a banking platform that processes thousands of credit card applications daily. The service acts as an assembly line, moving requests through various microservice stations—including account data retrieval via the AU service, error validation, bureau data collection via the CUBE service, and final decisioning—before publishing results to Kafka and a database.

The core challenge was implementing a new "Co-Owner Merge" feature. This feature required its own credit checks and risk assessments without interfering with the existing Business As Usual (BAU) credit line increase requests. To ensure a safe deployment from a single codebase and avoid costly errors like accidental bureau pulls or incorrect decisions, I focused on robust logic isolation and environment management.

Technically, the application runs on AWS ECS Fargate. While the current production system uses a Splunk Universal Forwarder for host-side log shipping, I have been working within a new application environment ([arsqa]) to manage logs specifically at var/log/arsqa/cdn-verification-service/app.log.

I believe this experience highlights my ability to scale complex orchestration services while maintaining system integrity during major feature rollouts.
