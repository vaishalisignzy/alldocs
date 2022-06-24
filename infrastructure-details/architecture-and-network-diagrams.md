# Architecture Diagram

![](<../.gitbook/assets/image (1).png>)

## Element wise Descriptions for architecture diagrams

1. Client devices - The mobile devices on which RM app runs.
2. Persist - File system where images can be transiently uploaded and generates a cryptic URL
3. Web layer - The web layer hosts front-end code files for the AS flow, nginx proxy\_pass configurations to relay requests to the application layer. Application layer - Hosts business logic and main backend of the overall application, the connectivity to the other systems like Finacle, iWorks etc are done from this layer.
4. Extraction/Fetch APIs - Signzy identity extraction and data fetch services like, PAN automatic extraction, ROC data fetch etc.
5. Signzy onboarding engine - The engine of Signzy that supports onboarding workflow state machines & helps in creation of user workflows.
6. MongoDB - Database for data storage of backend.
