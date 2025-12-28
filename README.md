# 🌐 EduPulse - API Gateway Service
> The unified entry point for all EduPulse microservices, providing intelligent routing, load balancing, and centralized security.

[![Spring Cloud Gateway](https://img.shields.io/badge/Spring_Cloud_Gateway-6DB33F?style=for-the-badge&logo=spring&logoColor=white)](https://spring.io/projects/spring-cloud-gateway)
[![Spring Boot](https://img.shields.io/badge/Spring_Boot-6DB33F?style=for-the-badge&logo=springboot&logoColor=white)](https://spring.io/)
[![Java](https://img.shields.io/badge/Java_21-ED8B00?style=for-the-badge&logo=openjdk&logoColor=white)](https://www.oracle.com/java/)
[![WebFlux](https://img.shields.io/badge/WebFlux-Reactive-blueviolet?style=for-the-badge)](https://projectreactor.io/)
[![JWT](https://img.shields.io/badge/JWT-000000?style=for-the-badge&logo=jsonwebtokens&logoColor=white)](https://jwt.io/)
[![Microservices](https://img.shields.io/badge/Architecture-Microservices-blue?style=for-the-badge)](#)

---

## 📖 Project Overview

The **API Gateway** is the single entry point for all client requests in the EduPulse microservices ecosystem. Built on **Spring Cloud Gateway** with **reactive WebFlux**, it provides intelligent request routing, CORS handling, load balancing, and can be extended with authentication, rate limiting, and monitoring capabilities.

This gateway abstracts the complexity of the microservices architecture, presenting a unified API interface to frontend applications while enabling independent scaling and deployment of backend services.

### 🏗 Architecture Role

The gateway acts as the traffic controller for the entire platform:

* **🔀 Request Routing:** Directs incoming requests to appropriate microservices based on path patterns.
* **🔐 Security Layer:** Can validate JWT tokens and enforce authentication before routing.
* **🌐 CORS Management:** Centralized cross-origin resource sharing configuration.
* **⚖️ Load Balancing:** Distributes traffic across multiple service instances.
* **📊 Monitoring:** Provides actuator endpoints for health checks and metrics.
* **🔄 Retry Logic:** Automatically retries failed requests to improve resilience.

---

## 🚀 Key Features

* **🔀 Intelligent Routing:** Path-based routing to 5 microservices (User, Class, Enrollment, Quiz, Admin).
* **⚡ Reactive Architecture:** Built on WebFlux for high-performance, non-blocking I/O.
* **🌐 CORS Configuration:** Pre-configured for frontend (localhost:5173) and admin (localhost:8085).
* **🔄 Automatic Retry:** Configurable retry logic for failed requests.
* **📊 Actuator Integration:** Health checks, metrics, and route visualization.
* **🔐 JWT Ready:** Prepared for centralized authentication (can be enabled).
* **🚫 Circuit Breaking:** Ready for fault tolerance patterns (optional).
* **🎯 Header Preservation:** Maintains original host headers and custom headers (X-User-Id).

---

## 🛠 Tech Stack

* **Framework:** Spring Cloud Gateway 4.3.0
* **Runtime:** Java 21, Spring Boot 3.5.0
* **Reactive Stack:** Spring WebFlux, Project Reactor
* **Monitoring:** Spring Boot Actuator
* **Security:** JWT Support (jjwt 0.12.5)
* **Build Tool:** Maven

---

## 📡 Route Configuration

### Service Routing Table

| Path Pattern | Target Service | Port | Description |
|-------------|----------------|------|-------------|
| `/api/users/**` | User Service | 8086 | Authentication, user management, grades |
| `/api/classes/**` | Class Service | 8081 | Classes, lectures, attendance |
| `/api/enrollments/**` | Enrollment Service | 8082 | Student enrollment management |
| `/api/quizzes/**` | Quiz Service | 8084 | Quizzes, assessments, results |
| `/admin/**` | Admin Service | 8085 | Admin dashboard, analytics |

### Gateway Access

All services are accessed through the gateway on **port 8090**:

```
Frontend/Client → http://localhost:8090/api/users/login
                                      ↓
                            API Gateway (8090)
                                      ↓
                           User Service (8080)
```





## 🔗 Related Services

- [👤 User Service](https://github.com/Bavinduyeshan/Edu-Pulse-User-Service)
- [📚 Class Service](https://github.com/Bavinduyeshan/Edu-Pulse_Class_Service)
- [📝 Enrollment Service](https://github.com/Bavinduyeshan/Edu-Pulse-Entrollment-Service)
- [🎯 Quiz Service](https://github.com/Bavinduyeshan/Edu-Pulse-Quiz_Service)
- [👨‍💼 Admin Service](https://github.com/Bavinduyeshan/Edu-Pulse_Admin_Service)
- 
---

<div align="center">

**Built with ❤️ for better education management**

⭐ Star this repository if you find it helpful!

</div>
