<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# APIs with Lambda + API Gateway

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-compute-api)

**Author:** Abdulrahman Abdulkadir  
**Email:** abdabdulkadir62@gmail.com

---

![Image](http://learn.nextwork.org/confident_turquoise_quiet_hyena/uploads/aws-compute-api_c9d0e1f2)

---

## Introducing Today's Project!

In this project, I will demonstrate how to build and deploy a serverless API using AWS Lambda and API Gateway. I’m doing this project to learn how to create RESTful endpoints that trigger Lambda functions, enabling scalable and secure backend services without managing servers.

### Tools and concepts

Services I used were AWS Lambda, Amazon API Gateway, and Amazon DynamoDB. Key concepts I learnt include Lambda functions for running backend logic without servers, API Gateway for exposing APIs securely to users, and how to connect and fetch data from DynamoDB. I also learnt how to document APIs in JSON, set up stages for deployment, and manage permissions and error handling in serverless applications.


### Project reflection

This project took me approximately 2–3 hours to complete. The most challenging part was configuring the Lambda function to interact properly with DynamoDB and troubleshooting permission errors. It was most rewarding to see the API respond successfully with real data and to publish working documentation that showcases what I built.


I did this project today to deepen my understanding of how AWS Lambda and API Gateway work together to power serverless APIs. This project met my goals by helping me build a real-world API, connect it to DynamoDB, and document everything professionally. It boosted my confidence in using cloud-native tools to solve practical problems.


---

## Lambda functions

AWS Lambda is a serverless compute service that lets you run code in response to events without managing servers. I'm using Lambda in this project to handle API requests by executing backend logic when triggered by API Gateway, making the application lightweight and scalable.


The code I added to my function will retrieve user data from the UserData table in DynamoDB using a userId passed as a query string parameter in an API request. It constructs a GetCommand to fetch the item from DynamoDB, then returns the data in JSON format with the appropriate HTTP status code. If the user is not found, it returns a 404 response. If an error occurs, it responds with a 500 error message.


![Image](http://learn.nextwork.org/confident_turquoise_quiet_hyena/uploads/aws-compute-api_a1b2c3d5)

---

## API Gateway

APIs are interfaces that allow different software systems to communicate with each other. There are different types of APIs, like REST, SOAP, and GraphQL. My API is a REST API, which allows clients to make HTTP requests to retrieve user data from a DynamoDB table using a Lambda function as the backend.


Amazon API Gateway is a fully managed service that makes it easy to create, publish, maintain, and secure APIs at any scale. I'm using API Gateway in this project to expose my Lambda function through a public HTTP endpoint, so users can make requests (like retrieving user data) using a URL.

When a user makes a request to the API Gateway URL, the request is passed to the connected AWS Lambda function. API Gateway acts as the front door, handling things like HTTP methods, parameters, and routing. The Lambda function then processes the request—like querying a DynamoDB table—and returns a response, which API Gateway sends back to the user in a proper HTTP format.

![Image](http://learn.nextwork.org/confident_turquoise_quiet_hyena/uploads/aws-compute-api_m3n4o5p6)

---

## API Resources and Methods

An API is made up of resources, which represent specific paths or endpoints that clients can interact with. Each resource corresponds to a part of the URL, like `/user`, and can have methods like GET, POST, PUT, or DELETE. In this project, I created a `/user` resource so that clients can request user data using a GET method that triggers my Lambda function.


Each resource consists of methods, which are actions that define how clients can interact with that resource. Common methods include GET (to retrieve data), POST (to submit data), PUT (to update data), and DELETE (to remove data). In my project, I used the GET method to fetch user data from DynamoDB through the Lambda function.


I created a GET method, which connects my API Gateway to the Lambda function. This method allows clients to send a request with a `userId` in the query string, triggering the Lambda function to fetch and return user data from the DynamoDB table.


![Image](http://learn.nextwork.org/confident_turquoise_quiet_hyena/uploads/aws-compute-api_c9d0e1f2)

---

## API Deployment

When you deploy an API, you deploy it to a specific stage. A stage is like a versioned environment (such as `dev`, `test`, or `prod`) that allows you to manage and test different iterations of your API. I deployed to a stage called `dev` so I could test the functionality of my API endpoint in a controlled environment before making it live for real users.


To visit my API, I used the Invoke URL provided by API Gateway, followed by the stage name and the resource path, and added the userId as a query parameter. The API displayed an error because the Lambda function didn’t have permission to access DynamoDB or the query parameter wasn’t passed correctly.


![Image](http://learn.nextwork.org/confident_turquoise_quiet_hyena/uploads/aws-compute-api_3ethryj2)

---

## API Documentation

For my project's extension, I am writing API documentation because it helps others understand how to use my API, what endpoints exist, what parameters are needed, and what responses to expect. You can do this in the API Gateway console by exporting the API in Swagger (OpenAPI) format as a JSON file, making it easy to share and maintain.


Once I prepared my documentation, I can publish it to an API Gateway stage, which makes the documentation accessible via a public URL. You have to publish your API to a specific stage because the documentation is tied to the deployed version of the API — this ensures that users see the correct methods, endpoints, and configurations that match that stage.


My published and downloaded documentation showed me a structured JSON file containing details about my API's resources, methods, parameters, and responses. It included the base path, available endpoints like `/userdata`, the supported HTTP method (GET), expected query parameters (e.g., `userId`), and response formats. This gave a clear technical overview of how to interact with my API.


![Image](http://learn.nextwork.org/confident_turquoise_quiet_hyena/uploads/aws-compute-api_z9a0b1c2)

---

---
