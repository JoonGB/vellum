# 📚 Vellum - Plataforma de Intercambio de Libros

[![Java 21](https://img.shields.io/badge/Java-21-orange?logo=openjdk)](https://openjdk.org/)
[![Spring Boot 3](https://img.shields.io/badge/Spring_Boot-3.3-blue?logo=spring)](https://spring.io/projects/spring-boot)
[![Kubernetes](https://img.shields.io/badge/Kubernetes-1.29-326ce5?logo=kubernetes)](https://kubernetes.io/)
[![License: MIT](https://img.shields.io/badge/License-MIT-green)](LICENSE)

**Plataforma cloud-native para intercambio de libros** con arquitectura de microservicios.  
Autenticación con Keycloak + JWT. Datos en PostgreSQL (transacciones) y MongoDB (chat).  
Comunicación asíncrona con RabbitMQ. CI/CD con Jenkins y análisis de calidad con SonarQube.

---

## 📊 Estado del proyecto

![GitHub last commit](https://img.shields.io/github/last-commit/JoonGB/vellum?color=blue)
![GitHub issues](https://img.shields.io/github/issues/JoonGB/vellum)
![GitHub pull requests](https://img.shields.io/github/issues-pr/JoonGB/vellum)

---

## 📦 Tech Stack

### 🖥️ Frontend
- **Framework principal:** [React 18](https://reactjs.org/) + [TypeScript](https://www.typescriptlang.org/)
- **Build tool:** [Vite](https://vitejs.dev/)
- **Rutas:** [React Router](https://reactrouter.com/)
- **UI & Estilos:**
  - [Tailwind CSS](https://tailwindcss.com/) (utility-first)
  - Iconos con [lucide-react](https://lucide.dev/) o Font Awesome
- **Gestión de estado:**
  - Global: React Context API / [Zustand](https://zustand-demo.pmnd.rs/)
  - Server State: [React Query](https://tanstack.com/query)
- **Formularios y validación:**
  - [React Hook Form](https://react-hook-form.com/)
  - Validación en backend con Hibernate Validator

---

### ⚙️ Backend
- **Lenguaje & Framework:** Java 21+ con [Spring Boot 3](https://spring.io/projects/spring-boot)
- **Arquitectura distribuida:** [Spring Cloud](https://spring.io/projects/spring-cloud)  
  - Gateway: Spring Cloud Gateway  
  - Service Discovery: Netflix Eureka  
- **Mensajería asíncrona:** [RabbitMQ](https://www.rabbitmq.com/)
- **Bases de datos:**
  - Relacional: PostgreSQL (user-service, book-service, exchange-service)
  - No relacional: MongoDB (chat-notification-service)
  - Almacenamiento de objetos: Amazon S3 / Google Cloud Storage
- **ORMs & Drivers:** Spring Data JPA (Postgres) y Spring Data MongoDB
- **Autenticación y seguridad:**
  - [Keycloak](https://www.keycloak.org/) para gestión de identidades (OAuth2/OIDC)
  - JWT para autenticación entre servicios
  - [Spring Security](https://spring.io/projects/spring-security)

---

### ☁️ Infraestructura
- **Contenerización:** [Docker](https://www.docker.com/)
- **Orquestación:** [Kubernetes](https://kubernetes.io/)
- **Cloud Providers:** Google Cloud Platform (GCP) o Amazon Web Services (AWS)

---

### 🛠️ Herramientas de desarrollo
- **Control de versiones:** Git + GitHub
- **CI/CD:** [Jenkins](https://www.jenkins.io/) (build, test, deploy)
- **Análisis de calidad:** [SonarQube](https://www.sonarqube.org/)

---

### 📊 Observabilidad
- **Métricas:** [Prometheus](https://prometheus.io/)
- **Dashboards:** [Grafana](https://grafana.com/)


```mermaid
graph TD
    A[Frontend React] --> B[API Gateway]
    B --> C[User Service]
    B --> D[Book Service]
    B --> E[Exchange Service]
    B --> F[Chat Service]
    C --> G[(PostgreSQL)]
    D --> G
    E --> G
    E --> H{{RabbitMQ}}
    F --> I[(MongoDB)]
    F --> H
    H --> J[Notification Service]
```

---

## 🤝 Contribución
Las contribuciones son bienvenidas 🙌  
Por favor, abre un **issue** o un **pull request** para sugerencias, mejoras o correcciones.

---

## 📄 Licencia
Este proyecto se distribuye bajo la licencia **MIT**. Consulta el archivo [LICENSE](LICENSE) para más detalles.
