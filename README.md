# Serverless Weather Application

This architecture is a web application that decouples a static S3 hmtl frontend from a scalable serverless backend. Utilized AWS Lambda and API Gateway to handle dynamic processing, optimizing infrastructure costs. Enhanced security posture by implementing credential management best practices including protecting sensitive API keys with Lambda Environment Variables.

## Architecture
* **Frontend**: Static assets (HTML/CSS/JS) served via S3 for high-performance delivery.
* **Backend**: AWS Lambda functions triggered by Amazon API Gateway to handle dynamic requests and manage sensitive API keys.
* **Integration**: Asynchronous fetch() calls from the client-side bridge the S3-hosted UI with the AWS-hosted API to return live weather data as structured JSON.

## Key Features
* **Hybrid Deployment**: Combines the speed of traditional web servers (Nginx) with the scalability of serverless compute (AWS).
* **Secure Data Handling**: Backend processing in AWS Lambda keeps weather service API keys hidden from the client-side.
* **Cost-Effective**: Utilizes pay-per-use cloud services for backend operations.

## Setup Instructions
1. **Frontend**: Deploy your static files to your Nginx server.
2. **Backend**: 
   - Deploy the APIRetriver Lambda function in AWS.
   - Configure Amazon API Gateway with an /weather route attached to the Lambda.
   - Set WEATHER_API_KEY in the Lambda Environment Variables.
3. **Connect**: Update your frontend fetch() URL to point to your new API Gateway endpoint.

---
*Built as an API cloud engineering project.*
