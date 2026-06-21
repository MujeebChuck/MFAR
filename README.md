# MFAR
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
