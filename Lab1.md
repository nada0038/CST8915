# LAB 1
### Front of Store (Vue.js)
The front-end web application through which consumers communicate with the pet shop is called the Store Front. Vue.js, a JavaScript framework that generates dynamic and responsive user interfaces, is used in its construction. Its functions include presenting product listings that have been obtained from the Product Service and offering an ordering interface. The Store Front serves as an interface between users and the backend services by interacting with the Order Service and Product Service via REST API requests.

### Order Service (Node.js)
The Order Service is a Node.js backend microservice. Orders from customers are received by it from the storefront, verified, and then sent to RabbitMQ for more processing. Order messages are consistently transmitted and not lost even in the event of high traffic via the use of a message queue. Every time an order is made, the Store Front makes a call to an API endpoint provided by the Order Service.

### Product Service (Rust)
The Product Service is a Rust-written microservice with a focus on dependability and efficiency. All product-related information, including names, pricing, and stock levels, is managed by it. To show clients the items that are available, the storefront queries this service. The Product Service communicates with the Store Front directly by providing REST APIs, guaranteeing proper product listings and real-time stock changes.

### RabbitMQ
RabbitMQ setup on the Azure virtual machine to serve as the message queue manager. It managed service-to-service communication, primarily order queuing from the Order Service. Then checked that order messages were being handled successfully by opening port 15672 and accessing the administration dashboard.