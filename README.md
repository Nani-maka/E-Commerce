#  Distributed E-Commerce Order Engine

##  Project Overview

This project is a **backend simulation of a scalable e-commerce system** inspired by platforms like Amazon and Flipkart.
It is designed to handle real-world challenges such as **inventory management, concurrent users, order processing, payment failures, and transaction safety**.

The system is built using **Python and FastAPI**, with a modular service-based architecture.

---

##  Features Implemented

###  Core Features

* Product Management (Add, Update, View)
* Multi-user Cart System
* Real-time Stock Reservation
* Order Placement Engine (Atomic operations)
* Payment Simulation (Success / Failure)
* Transaction Rollback System

---

###  Advanced Backend Features

* Concurrency Handling (Thread-safe locking)
* Order State Machine

  ```
  CREATED → PENDING_PAYMENT → PAID → SHIPPED → DELIVERED
                             ↘ FAILED
                             ↘ CANCELLED
  ```
* Discount & Coupon Engine

  * SAVE10 → 10% off
  * FLAT200 → ₹200 off
* Inventory Alert System (Low stock detection)
* Order Cancellation & Refund System
* Partial Returns Handling
* Event-Driven System (Queue-based processing)
* Inventory Reservation Expiry
* Audit Logging System (Immutable logs)
* Fraud Detection System
* Failure Injection System
* Idempotency Handling (Prevent duplicate orders)

---

##  Project Structure

```
E-Commerce/
│
├── app/
│   ├── main.py
│   ├── models/
│   ├── services/
│   ├── utils/
│
├── data/
│   ├── products.json
│   ├── carts.json
│   ├── orders.json
│   ├── logs.txt
│
├── README.md
└── requirements.txt
```

---

##  Tech Stack

* **Language:** Python 
* **Framework:** FastAPI
* **Server:** Uvicorn
* **Architecture:** Service-based modular design
* **Concurrency:** Threading Locks
* **Storage:** In-memory / JSON

---

##  How to Run the Project

###  Clone the Repository

```bash
git clone https://github.com/<your-username>/Ecommerce_Order_Engine.git
cd Ecommerce_Order_Engine
```

---

###  Create Virtual Environment (Recommended)

```bash
python -m venv venv
```

Activate:

**Windows:**

```bash
venv\Scripts\activate
```

---

###  Install Dependencies

```bash
pip install fastapi uvicorn
```

---

###  Run FastAPI Server

```bash
python -m uvicorn app.main:app --reload
```

---

###  Open in Browser

* API: http://127.0.0.1:8000
* Swagger Docs: http://127.0.0.1:8000/docs

---

##  Example API Endpoints

| Method | Endpoint  | Description       |
| ------ | --------- | ----------------- |
| GET    | /         | Health check      |
| POST   | /products | Add product       |
| GET    | /products | View all products |
| POST   | /cart/add | Add item to cart  |
| POST   | /order    | Place order       |
| GET    | /orders   | View orders       |

---

##  Design Approach

The system is divided into independent services:

* **Product Service** → Manages products & inventory
* **Cart Service** → Handles user carts
* **Order Service** → Processes orders & lifecycle
* **Payment Service** → Simulates transactions
* **Inventory Service** → Handles stock reservation
* **Event Service** → Manages event queue
* **Fraud Service** → Detects suspicious activity
* **Log Service** → Maintains audit logs

This ensures:

* Loose coupling
* High scalability
* Easy maintainability

---

##  Assumptions

* Single-machine simulation (not fully distributed)
* Payment gateway is mocked
* Data stored in memory/JSON (no database)
* CLI + API hybrid system

---

##  Future Improvements

* Convert to full microservices architecture
* Add PostgreSQL / MongoDB database
* Integrate Redis for caching
* Use Kafka/RabbitMQ for event streaming
* Deploy using Docker & Kubernetes
* Add authentication (JWT)

---

##  Author

**Nani (B.Tech CSE Student)**
Passionate about Backend Development & System Design 🚀

---

##  Conclusion

This project demonstrates real-world backend engineering concepts such as:

* Concurrency control
* Transaction safety
* Fault tolerance
* System design principles

It is highly suitable for **backend developer and data engineering roles**.

---
