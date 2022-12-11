# Application overview -

-   Distributed microservice architecture for high scalability.
-   Build on three services - _Payments_ , _Customer_ , _Frontend_.
-   All microserives are highly decoupled.
-   This app follows the Event driven architecture.
-   Frontend is made using **React JS** using the functional components.
-   For Database **MongoDB** is used .
-   **RazorPay** is used for doing payments .
-   **RabbitMq** is used as Message Queue for triggering events.
-   **NGINX** is used as reverse proxy for directing the requests over to the services.
-   [![Run in Postman](https://run.pstmn.io/button.svg)](https://app.getpostman.com/run-collection/15798447-846dfb27-1616-4c47-98ed-900384c93e64?action=collection%2Ffork&collection-url=entityId%3D15798447-846dfb27-1616-4c47-98ed-900384c93e64%26entityType%3Dcollection%26workspaceId%3D3700ddd4-1040-4ed4-aa63-2a0d2425cf01)
-   **ENV files:** [https://drive.google.com/drive/folders/1BH_2ZdRQfTeSWWMI-kf7HIR3_seh5pCQ?usp=sharing](https://drive.google.com/drive/folders/1BH_2ZdRQfTeSWWMI-kf7HIR3_seh5pCQ?usp=sharing)

## Setup Instructions

-   S1 Clone the project.
-   S2 Create a file .env in the root folder of all four services.ie ./Payments/.env , ./Customer/.env.
-   S3 Make sure that docker is installed in the system.
-   S3 Make sure that PORT 5000 , 5001 , 5002 , 3000 , 27017 are free in the system .
-   S4 Open terminal in root folder of the project where docker-compose.yml file is present and run following commands.

```bash
docker compose up
```

### To verify that all four services are running properly open the following four links in the browser

-   _http://localhost:5000/customer/status_
-   _http://localhost:5000/payments/status_

Each of them would give a message like : Customer service running properly , Payments service running properly

### To access frontend UI open the following link in the browser.
- _http://localhost:3000_

```bash

# To close application
docker compose down
```
### Architecture of the whole application
![Untitled Diagram-Page-1 drawio](https://user-images.githubusercontent.com/55759980/206905811-bd556672-ac85-43be-8309-0078978314af.png)

### About Project
- The Project is microservice based .
- It is based on 3 service : *Frontend* , *Customer* , *Payments*
- Payments and Customer services have their own databases which remain in sync with the help of a message queue.
- Rabbit Mq is used as a message queue with direct exchange .
- Both services Payment and Customer are using MongoDb databases .
- Each request to Backend is Redirected using the NGINX as the gateway.
### Below is the ER diagram model of the Customer and the Payments Services

![alt text](https://res.cloudinary.com/abhistrike/image/upload/v1670756312/Untitled_Diagram-Page-2.drawio_fj4dxb.svg)
