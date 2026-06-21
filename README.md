# MFAR
 I have summarized my recent project work on the banking platform’s orchestration service for our webpage display:

  - Developed an orchestration service for a high-volume banking platform processing thousands of daily credit card applications.
  - Managed an "assembly line" workflow integrating AU service (account data), error validation, CUBE service (bureau data), and final decisioning.
  - Implemented the "Co-Owner Merge" feature, enabling independent credit checks and risk assessments separate from BAU credit line increase requests.
  - Ensured safe deployment via logic isolation and environment management to prevent accidental bureau pulls or incorrect decisions from a single codebase.
  - Integrated automated data publishing to Kafka and internal databases for downstream processing.
