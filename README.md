# Systems-Engineering-student-focused-on-backend-development
Software Developer Portfolio – Systems Engineering student focused on backend development, system architecture, and cloud technologies.



# 🏦 Banking Solution Architecture – BP Internet Banking System

**Jonathan Llugsa**  
**27/02/2026**

---

## 📌 1. Introduction | Introducción

This document describes the architecture of an Internet Banking System for BP Bank. The solution is designed to be secure, scalable, and highly available for digital financial operations.

Este documento describe la arquitectura de un sistema de banca por internet para el Banco BP, diseñado para ser seguro, escalable y altamente disponible.

---

## 🎯 2. Functional Requirements | Requerimientos funcionales

- Account transaction history | Consulta de movimientos  
- Internal & interbank transfers | Transferencias internas e interbancarias  
- Notifications system | Sistema de notificaciones  
- Audit logging | Registro de auditoría  
- Biometric onboarding | Onboarding con reconocimiento facial  
- OAuth2 authentication | Autenticación OAuth2  

---

## ⚙️ 3. Non-Functional Requirements | Requerimientos no funcionales

- High availability | Alta disponibilidad  
- Fault tolerance | Tolerancia a fallos  
- Low latency | Baja latencia  
- Horizontal scalability | Escalabilidad horizontal  
- Security & data protection | Seguridad y protección de datos  
- Regulatory compliance | Cumplimiento normativo  

---

## ☁️ 4. Architecture Decisions | Decisiones de arquitectura

---

### 4.1 Cloud Platform | Plataforma en la nube

Microsoft Azure (PaaS) is selected as the main cloud platform.

Se selecciona Microsoft Azure como plataforma principal.

**Justification | Justificación:**
- Native integration with Azure AD B2C  
- High availability across regions  
- Reduced infrastructure management (PaaS model)  

---

### 4.2 Microservices Architecture | Microservicios

The system is designed using a microservices architecture by domain.

Arquitectura basada en microservicios por dominio:

- Customers Service | Servicio de clientes  
- Transactions Service | Servicio de movimientos  
- Transfers Service | Servicio de transferencias  
- Notifications Service | Servicio de notificaciones  
- Audit Service | Servicio de auditoría  

**Benefits | Beneficios:**
- Independent scaling  
- Fault isolation  
- Easier maintenance and evolution  

---

### 4.3 API Gateway

Single entry point for all system requests.

Punto único de entrada del sistema.

**Functions | Funciones:**
- OAuth2 validation  
- Routing  
- Security policies  
- Rate limiting  
- Monitoring  

---

### 4.4 SPA Application | Aplicación SPA

Angular is used for the web application.

Se utiliza Angular para la aplicación web.

---

### 4.5 Mobile Application | Aplicación móvil

Flutter is selected for cross-platform development.

Se selecciona Flutter por su desarrollo multiplataforma.

---

### 4.6 Authentication | Autenticación

Azure AD B2C with OAuth2 Authorization Code + PKCE flow.

Azure AD B2C con flujo OAuth2 Authorization Code + PKCE.

**Benefits | Beneficios:**
- Secure for SPA and mobile  
- Supports MFA  
- Industry banking standard  

---

### 4.7 Messaging System | Mensajería

Azure Service Bus is used for asynchronous communication.

Se utiliza Azure Service Bus para comunicación asíncrona.

**Benefits | Beneficios:**
- Event-driven architecture  
- Automatic retries  
- Decoupled services  

---

### 4.8 Databases | Bases de datos

Each microservice has its own database.

Cada microservicio tiene su propia base de datos.

**Benefits | Beneficios:**
- Data isolation  
- Better scalability  
- Reduced coupling  

---

### 4.9 Caching | Persistencia

Azure Cache for Redis using Cache-Aside pattern.

Redis Cache con patrón Cache Aside.

**Benefits | Beneficios:**
- Lower latency  
- Reduced load on core banking system  

---

### 4.10 Biometric Recognition | Reconocimiento facial

Azure Face API is used for identity verification.

Se utiliza Azure Face API para verificación de identidad.

**Benefits | Beneficios:**
- Fraud prevention  
- Strong identity validation  

---

## 🔄 5. System Overview | Descripción general

The system is accessed via SPA or mobile application, communicating through an API Gateway that routes requests to microservices connected to the core banking system.

El sistema se accede mediante SPA o aplicación móvil que consume un API Gateway.

**Flow:**
1. User authentication (Azure AD B2C)  
2. API Gateway receives request  
3. Microservices process business logic  
4. Core banking system validates transactions  
5. Events sent to Service Bus  
6. Notifications and audit logs generated  

---

## 🧱 6. Architecture (C4 Model)

---

### 🟦 6.1 Context Diagram | Diagrama de contexto

📌 Insert diagram here:

<img width="886" height="650" alt="image" src="https://github.com/user-attachments/assets/9016ac1c-8ae2-4547-9540-e5cb2e8ee44c" />


---

### 🟧 6.2 Container Diagram | Diagrama de contenedores

📌 Insert diagram here:

<img width="886" height="1057" alt="image" src="https://github.com/user-attachments/assets/dc56a5bf-5db0-4543-969b-9a26269ef848" />


---

### 🟩 6.3 Component Diagram | Diagrama de componentes

📌 Insert diagram here:

![C4 Components](./img/c4-component.png)

---

## 🧾 7. Audit Design | Diseño de auditoría

- Independent database per service  
- Immutable audit logs  
- Event-based tracking  
- Regulatory compliance  

---

## ⚡ 8. Caching Strategy | Patrón de cache

Redis Cache (Cache-Aside Pattern):

- If data exists → return immediately  
- If not → fetch from core system  
- Store result in cache  

---

## 🚀 9. High Availability | Alta disponibilidad

- Auto Scaling  
- Multi-instance deployment  
- Database replication  
- Automatic backups  
- Point-in-time recovery  

---

## 🔐 10. Security & Compliance | Seguridad

- OAuth2 + PKCE  
- HTTPS / TLS encryption  
- Azure Key Vault  
- ISO 27001 compliance  
- OWASP Top 10  
- Data protection laws  

---

## 📸 11. Biometric Onboarding | Onboarding biométrico

- User registration  
- Identity validation  
- Facial recognition  
- Multi-factor authentication  

---

## 📊 12. Monitoring | Monitoreo

- Centralized logs  
- Performance metrics  
- Alerts  
- Auto-healing mechanisms  

---

## 🧠 13. Conclusion | Conclusión

This architecture is secure, scalable, and cloud-native, following microservices and modern banking system principles.

Esta arquitectura es segura, escalable y moderna, basada en microservicios y cloud computing.
