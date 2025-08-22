# Real-Time E-Commerce Order Processor (Microservices with AWS)
Concept:
A serverless system that handles e-commerce orders end-to-end with event-driven workflows.

Microservices (AWS Lambda):
	•	Order Service (API Gateway + Lambda) → receives new orders, validates them, and saves to DynamoDB.
 
	•	Payment Service (DynamoDB Stream-triggered Lambda) → processes payment (simulate with Stripe sandbox).
 
	•	Inventory Service (SNS-triggered Lambda) → updates product stock in DynamoDB.
 
	•	Notification Service (SQS-triggered Lambda) → sends email/SMS confirmation via AWS SES/SNS.
 
	•	Analytics Service (Kinesis-triggered Lambda) → streams order data into S3 / Redshift for reporting.

Tech stack:
	•	Backend: AWS Lambda (C#)
	•	Data: DynamoDB (orders + inventory), S3 (logs/reports)
	•	Messaging/Events: API Gateway, DynamoDB Streams, SQS, SNS, Kinesis
	•	Frontend (Optional): React storefront UI to place/test orders
