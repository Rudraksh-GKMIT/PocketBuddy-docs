# Technical Stack with their Appropriate Versions

Below are the core technologies and tools used in **PocketBuddy**, along with their versions, usage areas, and reasons for selection.

| **Technology / Tool** | **Version** | **Usage in PocketBuddy** | **Reason for Choosing This Version** |
|------------------------|-------------|---------------------------|--------------------------------------|
| **HTML5** | 5.2 | Used for structuring the web pages including Login, Dashboard, Analytics, and Transaction views. | HTML5.2 provides semantic structure, accessibility, and native support for responsive layouts and PWA integration. |
| **JavaScript (ECMAScript 2022)** | ES13 / 2022 | Manages dynamic dashboard interactions, form validations, and API communications with the FastAPI backend. | ES2022 supports stable async/await, modular imports, and modern browser compatibility for seamless user interaction. |
| **Bootstrap** | 5.3.3 | Provides consistent, responsive, and mobile-first UI components for the PocketBuddy frontend. | Bootstrap 5.3 is optimized for performance, removes jQuery dependency, and ensures easy theming for dashboards. |
| **FastAPI** | 0.115.2 | Core backend framework managing authentication, transactions, and analytics APIs. | Latest stable release optimized for async I/O, includes Pydantic v2 support, and ideal for RESTful API design. |
| **Uvicorn** | 0.30.3 | ASGI server used to serve the FastAPI application. | Lightweight and highly performant perfectly compatible with FastAPI 0.115 for concurrent requests. |
| **PostgreSQL** | 15.6 | Primary relational database storing users, families, categories, and transaction data. | PostgreSQL 15.6 is stable, ACID-compliant, supports complex queries and indexing for financial analytics. |
| **SQLAlchemy** | 2.0.36 | ORM layer for database communication and schema modeling. | SQLAlchemy 2.0 supports full async features, modern query syntax, and integrates cleanly with FastAPI. |
| **Pydantic** | 2.5.3 | Used for validating request and response models in FastAPI. | Ensures robust data validation, reduces runtime errors, and integrates seamlessly with FastAPI’s dependency injection. |
| **Python** | 3.10.14 | Core backend programming language used to build the FastAPI server logic. | Python 3.10 introduces improved async performance and pattern matching, ensuring full compatibility with FastAPI stack. |
| **PWA (Progressive Web App)** | 2023 Standard | Enhances frontend usability allows installable app behavior and offline access for PocketBuddy users. | PWA standards provide secure HTTPS operation, caching, and cross-platform installability. |

---

### Summary of Stack Utilization
- **Frontend:** HTML5, CSS3, JavaScript (ES6+), Bootstrap 5.3, PWA  
- **Backend:** FastAPI 0.115, Uvicorn 0.30, SQLAlchemy 2.0, Pydantic 2.5  
- **Database:** PostgreSQL 15  
- **Language:** Python 3.10  

---

### Versioning Note
All selected versions are **stable releases** as of **November 2025**, ensuring long-term compatibility, active community support, and smooth integration across PocketBuddy’s modules and AWS deployment environment.
